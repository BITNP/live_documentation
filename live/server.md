# 服务器和网站

一般来说，提前一小时或以上打开直播间开始推测试视频，保证NPLive的可用性

## General

当前NPLive主站的后端SRS4（10.1.139.123:19350端口）+ Tornado框架开发的弹幕（10.1.139.100:8888） + MongoDB日志（10.1.139.100:8081），前端为Dplayer。

当前服务器使用docker-compose进行部署。

主站通过HLS（https 12443）提供直播服务。

## live.bitnp.net转发到bilibili设置

此项目已弃用，若需转推其他平台，请直接使用obs拉取nplive流(rtmp://live.bitnp.net:19350/nplive/livestream)后推送到对应平台。
