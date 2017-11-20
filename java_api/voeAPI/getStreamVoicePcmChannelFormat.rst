getStreamVoiceChannelPcmChannelNum
===============================
**获取流式文件数据的声道数**

1.接口说明

获取指定id的系统音效数据的声道数

2.函数原型
::

    int getStreamVoiceChannelPcmChannelNum(String id)

3.示例代码
::
    try{
        int tempChannelNum = client.getStreamVoiceChannelPcmChannelNum("1");
    } catch (IOException e) {
            e.printStackTrace();
    }
    
4.出错处理

出错时，函数返回-1。