GetRecordVoiceChannelNum
========================
**获取录制声音数据的声道**

1.接口说明

录音数据的位深度信息

2.函数原型
::
    int GetRecordVoiceChannelNum(ref uint32 channelNum)

3.示例代码
::
    uin32_t tempChannelNum = 0;
    client.GetRecordVoiceChannelNum(ref tempChannelNum);

4.出错处理

出错时，函数返回-1。