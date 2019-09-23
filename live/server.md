# 服务器和网站

- **一般来说，提前一小时或以上打开直播间开始推测试视频，保证nplive的可用性**

### live.bitnp.net转发到bilibili设置

- **注意:这个仅仅在推b站时才需要操作这一部分,只推nplive不用管这里**
- **这里需要熟悉docker的linux大佬ssh操作(血的教训)**

```shell
$ ssh root@live.bitnp.net
(Input password)
# ls
1080p.png ... nplive bash-tools nplive-deploy

--> nplive: 前端,一般不需要改
--> bash-tools: 登录校园网账号的脚本在这里
--> nplive-deploy: 直播系统的目录
```

```shell
# cd bash-tools
# ls
# ./login.sh        --> 向bilibili推流时需要在服务器用这个脚本登录校园网
usage ./login.sh username [password]
```

```shell
# cd ~
# cd nplive-deploy
# cd bitnp
# ls
... bitnp.conf ...

--> bitnp.conf是配置文件,别的东西一般不用动
```

```shell
# nano bitnp.conf

--> 编辑一下,也可以用vim
--> 这里我们直接翻到文件的最后面engine output部分,这里是bilibili转发的配置,别处一般不用改
--> 第一行配置enabled on;
--> 如果原来是enabled off需要改成on,推流结束最好改回off
--> 最后面形如output rtmp://bvc.live-send.acg.tv/live-bvc/?streamname=live......的配置
--> 这是推流地址,需要把推流直播间bilibili给的链接填到这里

# docker kill --signal=HUP srs_docker_name

--> bilibili推流设置结束
```

### jgsy.bitnp.net

jgsy.bitnp.net部署了旧系统，旧系统在OBS断线时，需要ssh登录服务器，重启nginx-rtmp

(等待填坑)

***