# OBS设置

## OBS推流设置

### 串流(右下角->设置->流)

|||
|-|-|
|主站|rtmp://live.bitnp.net:19350/nplive/livestream|
|当前ipv4地址|rtmp://10.1.139.123:19350/nplive/livestream|
|当前ipv6地址|rtmp://[2001:da8:204:2a05::123]:19350/nplive/livestream|

流密钥均为livestream

### 输出(右下角->设置->输出)

视频比特率 网络不好时:2500kb/s左右,网络状况好时:5000-8000kb/s

4G网络很不稳,建议1500kb/s左右,如有必要,可以继续下调,注意这时候要把输出分辨率调到1280*720.

编码器优先选择 QSV 或 AMD 或 NVENC，硬件加速编码，也可以用x264软压,CPU占用较高

HLS减小延迟：输出模式改为高级，设置关键帧间隔为2秒或3秒，以减少播放延迟。

录制视频可以修改一下录制视频质量，然后选择更高的码率，在推流码率低时使用

### 视频(右下角->设置->视频)

基础分辨率 1080p(1920*1080)

输出分辨率 1080p(1920*1080)

FPS 30 或 60，60fps仅在网络状态好的时候才能打开，请根据具体直播负载觉得是否使用。

### 添加视频捕获设备

来源->右键->添加->视频捕获设备->确定,设备选择采集卡(应该是那个驱动的名称),最下面打勾"使用自定义的音频设备",音频设备选择选择采集卡,确认

来源->视频捕获设备->右键->去隔行扫描（新版OBS翻译为“反交错”）-> Yadif 2x （如果视频源和OBS均未开启去隔行扫描，则会出现移动物体边缘出现大量撕裂的条纹，因此在每次重新创建视频捕获设备时要记得打开此选项）

如果输入的音频为单声道，混音器->视频捕获设备->高级音频属性->视频捕获设备打勾"单声道"**(如果想要让OBS把声音输出到扬声器或耳机可以在音频监听选择"监听并输出")**

## OBS场景设置

TODO
