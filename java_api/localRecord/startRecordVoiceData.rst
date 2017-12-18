startRecordVoiceData
====================

**开启语音消息录制**

1.接口说明

开始录制语音消息，需要先调用Init函数之后调用该函数。(可以本地录音，无需联网)语音数据可在注册的回调中获得。

2.函数原型
::

    int startRecordVoiceData();

3.示例代码
::
    
    client.startRecordVoiceData();

4.出错处理

出错时，函数返回-1。