controlChannel3DVoiceSwitch
============================
**3d音效开关**

1.接口说明

3d音效开关，默认对于所有听取的用户生效
播放文件时最好是在播放前设置好是否开启3d音效

2.函数原型
::
    int controlChannel3DVoiceSwitch	(boolean open)

3.示例代码
::
    client.controlChannel3DVoiceSwitch(true);

4.出错处理

出错时，函数返回-1。