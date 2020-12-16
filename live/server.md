# 服务器和网站

一般来说，提前一小时或以上打开直播间开始推测试视频，保证NPLive的可用性

## General

当前NPLive主站的后端SRS3.0（1935）+ Tornado框架开发的弹幕（8888） + MongoDB日志（8081），前端为Dplayer，支持网页端管理的NPLive-NG后端正在开发中。

当前服务器使用docker-compose进行部署。

主站主要通过HTTP-FLV（8080）和HLS（80）提供直播服务。

NPLive-NG部署后此页将更新。

## live.bitnp.net转发到bilibili设置

- **注意:这个仅仅在推b站时才需要操作这一部分,只推nplive不用管这里**
- **这里需要熟悉docker的linux大佬ssh操作(血的教训)**

登陆一下校园网，推流不计流量（上传），但是不登陆还是不能用
``` 
$ ssh root@live.bitnp.net
(Input password)
# cd bash-tools/
# bash ./login.sh username [password]
```

目前直播目录在`~/nplive-ng-backend-legacy`
SRS配置文件在`~/nplive-ng-backend-legacy/deploy/srs.conf.d`
编辑配置文件srs.conf，用nano，vim都行
```
# nano srs.conf
```

- 编辑一下,也可以用vim，这里我们直接翻到文件的最后面engine output部分,这里是bilibili转发的配置,别处一般不用改
第一行配置enabled on;
- 如果原来是enabled off需要改成on,推流结束最好改回off
- 最后面形如output rtmp://bvc.live-send.acg.tv/live-bvc/?streamname=live......的配置
- 这是推流地址,需要把推流直播间bilibili给的链接填到这里

改完之后保存退出编辑器，SRS会自动重新加载配置文件，不需要`docker kill`手动触发

注意由于当前使用了`supervisor`来管理SRS和nginx，向容器发送`SIGHUP`是发送给了`supervisor`，这将导致SRS和nginx重启，服务会暂时中断，请谨慎使用

目前有b站视频推流卡住的问题，经分析发现ffmpeg卡死了，怀疑是校园网断流导致的。`SIGHUP`重启服务可以解决，不过因为这样会服务中断，所以还是建议使用`docker exec`开一个shell进去，手动把卡死的ffmepg杀掉，就可以恢复了。

### 更详细的修改说明

用 `nano` 打开 `srs.conf` 后进行编辑。在文末找到 `engine outout {...}`

```
engine output {
	enabled         off;
	perfile {
		re;
	}
	vcodec          copy;
	vparams {
	}
	acodec          copy;
	aparams {
	}
	output          rtmp://live-push.bilivideo.com/live-bvc/?streamname=live_89756733_9652607&key=5275d5d2b210defdb1b172fda63e0ff4&schedule=rtmp;
}
```

如果要开始直播，看到最后的 `engin output {...}` 项，把其中的

```
enabled off;
```

改成

```
enabled on;
```

同时把 `output` 项后对应的直播地址 `rtmp://...` 改成要推流的对应地址。获取b站的直播地址可以 `鼠标悬停头像->进入“直播中心”->“我的直播间”->点击“开始直播”`，将出现的 `你的rtmp地址` 和`你的直播码` 两项内容前后拼接然后写入到 `engin output {...}` 项的 `output` 项的位置。

```
output rtmp://live-push.bilivideo.com/live-bvc/?streamname=live_89756733_9652607&key=5275d5d2b210defdb1b172fda63e0ff4&schedule=rtmp;
```

如果需要推流到多个地址，那么可以在 `engine output {...}` 项后头添加 `engine output2 {...}`等更多项，对应的配置方法和 `engine output {...}` 一致。
