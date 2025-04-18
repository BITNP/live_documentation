# NPLIVE 直播准备工作

## 人员配备

- 一般三人及以上,一人主推,一人监测直播状况,一人机动

- 大型直播强烈建议,有熟悉直播过程的大佬在场,处理各种突发问题

***

## 准备阶段

### 直播前准备(软硬件)

1. 安装必要的驱动及直播软件(详见直播群,群文件)

- 目前协会有一个新的采集卡和旧的采集卡，新采集卡是免驱的；旧采集卡驱动[点此下载](https://www.yuan.com.tw/support/download/driver/ub530-series-driver.zip)
- OBS[官网在此](https://obsproject.com/)

- 对于OBS的参数设置问题，参见[OBS配置](./obsconf.md)

2.准备必要的器材,一般所有的器材都统一放在一个大包中,包平时放在诊所或3B-314保管)

- 网线(带线轴,也可能同时还有无线轴的备用网线)
- 剪刀胶带(线路过长时应当固定,以免被人群踢断电源或者网线)
- 视频信号采集卡及连接线(黑色盒状,USB3.0,可接收HDMI和SDI信号,切换方法见下)
- 插板(2+个)
- HDMI线(很长,平时卷起来)
- 信号源的连接线一般由负责信号源的一方提供.
- 其他选带项目
  - 路由器1-2台(用来保证网络的稳定)
  - 过线桥(应对线路经过人流密集区域的情况)
  - 网线连通性测试工具

3.准备推流及监视设备(两台或以上笔记本)

- 用于进行视频流的推流;
- 检查服务器状态以及视频流的流量是否正常;
- 检测播放页面上的直播是否正常进行;观察画质、流畅度等是否符合要求;及时向推流设备或信号源反应情况.

### 每次直播前

1. 提前测试好所有直播设备和服务器相关配置
   - 测试完成后,原则上,确定直播方案并测试完成后设置均不再改动
2. 涉及摄像机问题,请尽快解决
   - 负责人提前联系摄像负责人(学习/学电/记者团),协调输入信号.
   - 询问输入方式,确定我们推流机器的位置.
   - 有条件时(一般是军理课),可以提前测试输入信号.
3. 准备好所需要的器材.(如有必要,可以提前布线)

***

## 直播具体操作

### 播前: 踩点

1. 找到属于自己的直播位置,并在直播位置附近寻找好电源进行连接;
2. 找到直播位置附近可用的网络端口并检查其是否可用以及是否稳定;
3. 预估在直播地点布线的难度和工作量;
4. 检查器材能否正常使用并且保持稳定;
5. **检查设备上的采集卡驱动是否已经成功安装并且采集卡是否能正常工作(此时采集卡指示灯为黄色)（红色说明驱动安装有问题，灯黄色但是OBS找不到采集卡请检查windows 10的相机访问权限，在设置，隐私里）;**
6. 检测设备是否能在推流与监控的情况下稳定高效的运行,排除由于设备的不稳定性所造成的直播的中断或者卡顿以及无法正确调试等问题.

### 当天:(根据预估情况,提前足够的时间到场)

1. 首先布线,布置电源线以及网线,测试电源稳定后运行设备,测试网络情况,布置1~2台路由器并其测试网络状况. ***(注意！必须检测路由器网络是否稳定可用！)***

2. 上述工作完成后,由技术人员首先检查推流服务器的状况,检查必要配置.可使用自己的测试视频测试推流

3. 连接采集卡,并且与信号源进行连接.在OBS上进行相关的配置,选择最稳定的设备推流,保证流的稳定.尽早完成本项，很多时候视频源需要调很久，可能有玄学问题

   **PS:** 信号源的不稳定要及时反应并且和信号的提供者进行沟通,尽快解决.

4. 进行尝试性的推流,在nplive/bilibili上观看直播,确定直播的音视频能否正常播放,是否出现卡顿的情况.若有,适当调节OBS中的设置(详见前述部分).

***

## 布线规则

1. 网线和光纤采用**两条**各自适合的线路,并且用**绝缘胶带**将线路尽量固定在**墙角**,因为光纤比较脆弱,还可以使用网线保护光纤的方法,当然如果没有使用光纤就直接布网线就可以了.

2. 尽量走直线,并选择人流较少的地方走线.

3. 对于人群踩踏较多的地方,比如门口,道路的位置适当利用过线桥进行加固,

4. 可以从墙上过线绕过门口可以从墙上绕过去.

   **绝缘胶带是直播设备固定的好帮手,可防止由于线材松动导致的断流(尤其路由器电源较松，容易断开，必须固定好保护好).另外应该更加注意提前对风险做好应对方案,到现场再现想解决方案风险较大.**

5. 光纤要求开始和结束处都要有电源（光纤转RJ45）。
