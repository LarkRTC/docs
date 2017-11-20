GetRecordVoiceMaxSamplateCount
==============================

**获取录制声音数据的采样点个数**

1.接口说明

录音数据的最大采样点个数

2.函数原型
::
	
    int GetRecordVoiceMaxSamplateCount(ref uint32_t maxSamplateCount)

3.示例代码
::
    uint32_t tempSamplateCounts = 0;
    client.GetRecordVoiceMaxSamplateCount(ref tempSamplateCounts);

4.出错处理

出错时，函数返回-1。