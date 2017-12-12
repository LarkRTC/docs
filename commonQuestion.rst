常见问题
========

| **1.某些函数调用后并没有回调**
| 1)回调的注册需要在相应函数调用之前
|
| **具体用法详解:** 
| demo_

| **2.无法听到对方的声音**
| 1)保证你注册成功并且发送相应请求(play or listen)
| 2)保证双方加入同一个房间
| 3)保证双方打开了扬声器和麦克风
| 4)Android系统保证开启录音权限

.. _demo: http://www.baidu.com/

| **3.文件播放不正常**
| (以unity接口为例)
| 1)首先保证你创建了播放文件的channel,就是CreateStreamVoiceChannel/CreateMediaFile函数
| 2)相应的文件信息利用相应的set函数设置进去了
| 3)指定的id或者path正确
| 4)播放前调用InitMediaFileConfig/InitSystemChannelConfig函数使配置生效
|

| **4.3d音效没有开启**
| (以unity接口为例)
| 1)首先在设置向量之前首先需要调用Enable3DVoice函数开启3d音效，然后才能设置相关向量
| 2)你确定与3d音效相关的向量设置正确
| 3)SetSpeakerPosition函数的设置需要在create相应的channel之后才能设置成功