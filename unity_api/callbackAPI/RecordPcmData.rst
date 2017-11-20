RecordPcmData
=============
**注册语音消息录制回调**

1.接口说明

注册语音录制消息回调，调用StartRecordVoiceData函数之后就会抛出该回调事件来抛出声音数据

2.函数原型
::
    int RegisterRecordPcmData(RecordPcmVoiceData  recordData)
    RecordPcmVoiceData :(void*)(byte[] data, ushort dataLen)

**录音数据的具体参数(采样率，位深度，声道数)可以通过相关的Get函数获取**

3.示例代码
::
    client.RegisterRecordPcmData(RecordData);
    
    void RecordData(byte[] data, ushort dataLen){

    }    

4.出错处理

出错时，函数返回-1。
