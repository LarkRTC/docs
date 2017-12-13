SetFileChannelFormat
===============================
**设置媒体文件数据的声道数**

1.接口说明

设置指定id的媒体文件数据的声道数

2.函数原型
::
    enum ChannelFormat
    {
        MONO = 1,       //< 1 channel
        STEREO = 2,     //< 2 channels
    };
    int SetFileChannelFormat(string id, ChannelFormat channelNum)

3.示例代码
::
    ChannelFormat tempChannelNum;
    client.SetFileChannelFormat("1",ChannelFormat::MONO);

4.出错处理

出错时，函数返回-1。