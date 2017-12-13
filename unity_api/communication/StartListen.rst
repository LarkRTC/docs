StartListen
===========
**开始听某人声音**

1.接口说明

(需要先调用CreateChannel创建管道)听别人说话，id即为对方register时传递的userID，必须保证双方的APPID与ROOMID相同才能互相连麦。

2.函数原型
::

    int StartListen(string id);

3.示例代码
::
    
    client.StartListen("1");

4.出错处理

出错时，函数返回-1。