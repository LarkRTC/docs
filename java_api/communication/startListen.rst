startListen 开始听某人声音
=============================

**开始听某人声音**

1.接口说明

(需要先调用call)听别人说话，id即为对方join时传递的userID，必须保证双方的APPID与ROOMID相同才能互相连麦。

2.函数原型
::
    int startListen(final String id);

3.示例代码
::
    client.startListen("1");

4.返回值

错误返回错误码，0表示设置成功。
