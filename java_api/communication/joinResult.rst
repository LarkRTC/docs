joinResult 加入房间异步结果
=============================

**网络注册是否成功回调**

1.接口说明

 注册是否成功的回调事件，调用join函数之后就会抛出该回调事件来通知是否注册成功。

2.函数原型
::
    int setJoinResultHandler(IJoinResult  result)
    IJoinResult:(void*)(int)

3.示例代码
::
    client.setJoinResultHandler(joinResult);
    
    void joinResult(int code)
    {
       
    }  

