getRecordVoiceDataFormat
========================
**获取录制声音数据的位深度**

1.接口说明

录音数据的位深度信息

2.函数原型
::
	
    int getRecordVoiceDataFormat()

3.示例代码
::
    try{
        int tempFmt = client.GetRecordVoiceDataFormat();
    } catch (IOException e) {
            e.printStackTrace();
    }

4.出错处理

出错时，函数返回-1。