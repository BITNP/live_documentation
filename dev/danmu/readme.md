# 弹幕系统

## 动机

模仿 bilibili 等视频平台的弹幕系统，提供一个能够有足够管控能力的弹幕平台，提升直播的在线体验。


**注意： 这部分的成本一定要让甲方提供**


## 需求与目标

- 支持千/万人级别
- 实名认证
- 可以选择审核通过后发送、撤回、自动过滤关键字等功能
- 多人审核

## 分析

现在网协的直播方式就弹幕问题可分为两种：

1. 直接使用现场大屏幕，往往不需经过网络
2. 传统的直播，通过网页访问

对于前者，我们可以充分利用现有的弹幕服务，如：

- [好弹幕](https://www.haodanmu.com/)
- [弹幕派](http://www.danmakupie.com/)

都是免费且功能较为完善的平台，此外也有许多更好(?)的付费平台。

而对于校内直播，可能目前比较好方案是进行自研。
对此我们需要：

- web 端弹幕插件，提供登录、收发弹幕等功能（这部分轮子比较多）
- 高并发、易扩展、安全的服务端应用（同下）
- 管理界面，web 或者其他（这部分如果没有框架就只能自己搞了）
- 恰当的运维（emmmmm）

其余还要解决

- 认证问题（其实也是安全策略的一部分）
- 安全策略
- TODO

