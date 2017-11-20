netError
========
**注册网络错误回调**

1.接口说明

注册网络错误回调函数。如若发生网络错误(例如 远程服务器关闭,被同名id挤下线, 客户端未连接网络等等)，会抛出回调事件
可以先调用DeRegister()断开服务器连接然后调用Register()重新鉴权达到断线重连的目的。


2.函数原型
::
    int RegisterNetError(NetErrorHandle netError)
    NetErrorHandle:(void*)()

3.示例代码
::
    client.RegisterNetError(HandleNetError);
    
    void HandleNetError(){
    
    }    

4.出错处理

出错时，函数返回-1。