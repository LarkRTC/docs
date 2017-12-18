JoinResult 加入房间异步结果
=============================

**加入房间异步结果回调**

1.接口说明

 注册是否成功的回调事件，调用Join函数之后就会抛出该回调事件来通知是否注册成功。

2.函数原型
::
    int SetJoinResultHandler(JoinResult  result)
    JoinResult:(void*)(int)

3.示例代码
::
    client.HandleRegisterResult(RegisterResult);
    
    void RegisterResult(int  code)
    {
        if (code == 0)
        {
            UnityEngine.Debug.Log("client.Register successful ");
        }
        else
        {
            UnityEngine.Debug.Log("client.Register failed ");
        }
    }  

