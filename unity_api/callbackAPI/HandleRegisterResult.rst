HandleRegisterResult
====================
**网络注册是否成功回调**

1.接口说明

 注册是否成功的回调事件，调用Register函数之后就会抛出该回调事件来通知是否注册成功。

2.函数原型
::
    int HandleRegisterResult(RegisterResult  result)
    RegisterResult:(void*)(bool)

3.示例代码
::
    client.HandleRegisterResult(RegisterResult);
    
    void RegisterResult(bool isSuccessful)
    {
        if (isSuccessful)
        {
            UnityEngine.Debug.Log("client.Register successful ");
        }
        else
        {
            UnityEngine.Debug.Log("client.Register failed ");
        }
    }  

4.出错处理

出错时，函数返回-1。