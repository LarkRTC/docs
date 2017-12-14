otherVad 人声检测
================

**注册其他用户人声检测回调**

1.接口说明

注册静音检测回调函数,init之后数据就会抛出,每20ms调用一次。

2.函数原型
::
    int setOtherVadHandler(OtherVad vadObverser)
    otherVad:(void*)(final String userID, boolean isSpeech)

- isSpeech: 0(此时未检测到人声)
- isSpeech: 1(检测到人声)


3.示例代码
::
    client.setSelfVadHandler(GetVad);
    
    void GetVad(fina String userID,boolean isSpeech){
      
    }    

4.返回值

错误返回错误码，0表示设置成功。