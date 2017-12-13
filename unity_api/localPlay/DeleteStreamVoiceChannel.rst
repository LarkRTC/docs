DeleteStreamVoiceChannel
==============================
**删除流式文件播放管道**

1.接口说明

删除一个用于播放流式系统音效的channel

2.函数原型
::
	
    int DeleteStreamVoiceChannel(string id)

3.示例代码
::
    client.DeleteStreamVoiceChannel("streamChannel");

4.出错处理

出错时，函数返回-1。
