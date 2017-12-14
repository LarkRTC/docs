流式播放音频
================

**流式播放音频**

1.接口说明

流式播放音频数据，每10ms引擎回调取10ms音频数据。如若填充了数据，在回调函数中返回true，如若播放完毕，在回调函数中返回false

2.函数原型
::
    | int playStreamVoice(final String id, INeedAudio needAudio, SampleRate sampleRate  
    |                                                            ChannelFormat channelFmt,
    |														     Format fmt);
    | INeedAudio:(boolean*)(final String id, byte[] data, int dataLen)


3.示例代码
::



4.出错处理


