InitSystemChannelConfig
===============================
**初始化流式文件配置**

1.接口说明

初始化外部设置的流式文件配置

2.函数原型
::

    int InitSystemChannelConfig(string path);

3.示例代码
::
    int ret = client.InitSystemChannelConfig("xxx")
    
4.出错处理

出错时，函数返回-1。