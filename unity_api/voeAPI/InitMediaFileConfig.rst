InitMediaFileConfig
===============================
**初始化媒体文件配置**

1.接口说明

初始化外部设置的媒体文件配置

2.函数原型
::

    int InitMediaFileConfig(string path);

3.示例代码
::
    int ret = client.InitMediaFileConfig("xxx")
    
4.出错处理

出错时，函数返回-1。