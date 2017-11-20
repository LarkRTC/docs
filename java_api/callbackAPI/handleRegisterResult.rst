handleRegisterResult
====================
**网络注册是否成功回调**

1.接口说明

 注册是否成功的回调事件，调用Register函数之后就会抛出该回调事件来通知是否注册成功。

2.函数原型
::
    int handleRegisterResult(IRegisterResult  result)
    IRegisterResult:(void*)(boolean)

3.示例代码
::
    client.handleRegisterResult(RegisterResult);
    
    void RegisterResult(bool isSuccessful)
    {

    }  

4.出错处理

出错时，函数返回-1。