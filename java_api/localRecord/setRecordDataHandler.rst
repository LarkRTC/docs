setRecordDataHandler 设置录音数据回调
=========================================

**开启语音消息录制**

1.接口说明

设置录音数据回调，开启录音后每10ms抛出数据，开发者可自由对数据进行操作，此处不应进行耗时操作，避免录音数据延迟甚至不完整。


2.函数原型
::
    int setRecordDataHandler(IRecordVoice recordData);
	IRecordVoice(void*)(byte[] data, SampleRate sampleRate, ChannelFormat channelFmt, Format fmt);

3.示例代码
::
    


4.出错处理


