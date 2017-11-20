CreateChannel
=============
**创建声音管道**

1.接口说明

创建和指定id(想要听的人)的声音管道，初始化管道环境。

2.函数原型
::

    int CreateChannel(string id);

3.示例代码
::
    
    client.CreateChannel("1");

4.出错处理

出错时，函数返回-1。