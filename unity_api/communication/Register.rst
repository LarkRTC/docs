Register
========
**音频服务注册**

1.接口说明

网络服务注册，只有注册过后才能使用后续网络服务(例如实时语音对话等)。该API是异步实现，是否注册成功需要在RegisterResult回调函数中获得结果。
调用该API之后肯定会触发RegisterResult回调函数(需要先注册回调)。

2.函数原型
::
    
    int Register(string appID, string appKey, string userID, int mode, string roomID);

- 参数说明：

======== =========== ========================================================================= 
参数      类型        说明                                                                     
======== =========== ========================================================================= 
appID      string      | 用于服务鉴权                                                            
appKey     string      | 用于服务鉴权                                                            
userID     string      | 玩家唯一的身份标识                                                      
mode       int         | mode设计分为主播模式（mode=1）和听众模式（mode=2),       
                       | 听众只能收听语音不能发送语音，而主播既可以发送语音也可以收听语音        
roomID     string      | 房间ID,只有相同房间的人才能进行互相通讯                                 
======== =========== ========================================================================= 


3.示例代码
::
    
    client.Register("fef68f5cf1a1ad61", "95dc07bda45acba098b83f8ed29e460d", "1", 1, "1");

4.出错处理
::
    ErrorCode:
      NOT_INIT = 1,
      INVALID_PARAMETER = 2,
      RECONNECTING =3,

