StopListen
==========
**停止听某人声音**

1.接口说明

(停止后可调用DeleteChannel删除管道,用于释放资源)停止听对方说话，id为对方register时传递的userID。

2.函数原型
::

    int StopListen(string id);

3.示例代码
::
    
    client.StopListen("1");

4.出错处理

出错时，函数返回-1。