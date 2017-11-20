deleteChannel
=============
**2.9 销毁声音管道**

1.接口说明

删除和指定id(想要听的人)的声音管道，销毁管道环境。

2.函数原型
::

    int deleteChannel(string id);

3.示例代码
::
    
    client.deleteChannel("1");

4.出错处理

出错时，函数返回-1。