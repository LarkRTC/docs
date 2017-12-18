stopListen 停止听某人声音
===========================

**停止听某人声音**

1.接口说明

(停止后可调用hangup删除管道,用于释放资源)停止听对方说话，id为对方join时传递的userID。

2.函数原型
::
    int stopListen(final String id);

3.示例代码
::
    client.stopListen("1");

4.返回值

错误返回错误码，0表示设置成功。
