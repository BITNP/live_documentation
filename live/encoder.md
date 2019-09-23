# HDMI Encoder文档

## What is?

HDMI Encoder可快速、低延迟地将输入到设备的HDMI信号推送网络流，而无需电脑进行软件推流。缺点是只能推送HDMI原始信号，无法像OBS那样设置丰富的场景，因此本设备并不常用。

## 需要设备

HDMI Encoder、电脑、路由器、网线、HDMI线

## 用法

### 推NPLIVE

将电脑和HDMI Encoder连接到路由器上，路由器WAN接入校园网。

要求路由器地址为192.168.1.1

HDMI Encoder的账号/密码为admin/admin，IP地址固定为192.168.1.168，网关192.168.1.1，浏览器访问192.168.1.168可进入管理页面。

编码器的主码流选择H264编码，不要选择H265，NPLIVE的SRS不支持H265编码。

RTMP PUSH URL填写`rtmp://live.bitnp.net/nplive/livestream`

推流状态可在Encoder的主页看到，显示已连接即说明已经开始推流。

### 其他功能

HDMI Encoder支持多个流推送，设置界面打开相关功能即可。

HDMI Encode支持自己做服务器，不推送到其他直播服务器。在主码流处打开相关流即可用。

功能不常用，仅作简单说明。
