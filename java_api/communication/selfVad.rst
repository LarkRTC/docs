selfVad 人声检测
================

**注册自己人声检测回调**

1.接口说明

注册静音检测回调函数,init之后数据就会抛出,每20ms调用一次。

2.函数原型
::
    int setSelfVadHandler(selfVad vadObverser)
    selfVad:(void*)(boolean isSpeech)

- isSpeech: 0(此时未检测到人声)
- isSpeech: 1(检测到人声)


3.示例代码
::
    client.setSelfVadHandler(getVad);
    
    void getVad(bool isSpeech){
    }    

4.返回值

错误返回错误码，0表示设置成功。