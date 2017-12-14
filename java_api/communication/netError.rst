netError 网络错误
=====================

**注册网络错误回调**

1.接口说明

注册网络错误回调函数。如若发生网络错误(例如 远程服务器关闭,被同名id挤下线, 客户端未连接网络等等)，会抛出回调事件


2.函数原型
::
    int setNetErrorHandler(INetError netError)
    INetError:(void*)()

3.示例代码
::
    void handleNetError(){
         
    }    
    client.setNetErrorHandler(handleNetError);
    

4.返回值

设置回调返回错误码，0表示设置成功。

