# -syb-
# 河北科技师范学院SYB培训刷课软件
> - 本项目供学习交流使用，使用本项目造成的一切后果自行承担
> - syb培训指《中仕学社技能提升》微信小程序中的培训课程。仅适配了科师学生。
> - 本软件仅支持刷第一门培训课程，若存在多门培训课程。请自行修改代码。

## config.py为配置文件，里面都有注释说明

**该软件分为多线程和单线程两种模式。可在config文件中切换**
**软件支持人脸识别，默认开启，可在config文件关闭。关闭人脸识别模式为绕过人脸。依然可以刷课。但是不保证后台有无异常。**

#### 代码说明：
- **1，python测试环境为：3.11.4 未在其他版本环境下测试。**
- **2，sign变量不确定是否必须，经测试多个账号下相同sign依旧无异常。**
- **3，client_id、client_key变量不确定是否固定，多个账号的两个变量值是相同的。多个微信也是。但不保证有变化的可能性。**
- **4，曾尝试过直接上报视频总时长来一次性完成视频的效果是可行的。但是频繁使用会导致接口返回异常，暂未找到解决办法。**
- **5，官方小程序的人脸识别原理为：每次开始视频播放时采集人脸。播放过程中每隔12分钟自动暂停视频。需要手动播放，播放又需要采集人脸，从而达到视频播放过程中不断的采集人脸。**

#### 软件说明：
- **1，多线程模式下10-20线程为最佳。尽量不要开启过多线程。**
- **2，小程序官方记录时长间隔为30秒一次。但经测试该小程序未做时长检测，因此频繁发包可以实现秒刷效果。**

#### 关于人脸识别的说明：

> 人脸识别为了实现每次识别都是不同图片的效果。采取的模式为选取视频中的关键帧作为采集图像。
> 
- **1，首先录一个大概10秒左右的视频，视频尽量保证每时每刻你的姿势都不一样。不然关键帧中图片会有较大的相似。拍摄过程中尽量不要眨眼。**
- **2，然后将录制好的视频放在main.py的同目录下，并重命名视频文件为：video.mp4**
- **3，运行软件，若无异常的话，会在同目录下生成image文件夹，并将视频所有的图片帧存入到该文件夹中，每次人脸采集时均会随机挑选该文件夹中的某个图片进行上传。**


#### 使用前请先安装依赖
```bash
pip install -r requirements.txt
```

> #### 作者有话说：
> 该软件是为了方便大四学生在写毕业论文期间节省不必要的时间而研究，研究的初衷是为了让大四学生有更好的学习效率，切勿用此软件进行二次倒卖。
> 本作者已从科师毕业，所有项目不再维护，不保证程序的正常运行。
