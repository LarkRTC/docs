VadObserver
===========
**注册静音检测回调**

1.接口说明

注册静音检测回调函数,init之后数据就会抛出,每20ms调用一次。

2.函数原型
::
    int RegisterVadObserver(VadObverser vadObverser)
    VadObverser:(void*)(bool isSpeech)

- isSpeech: 0(此时未检测到人声)
- isSpeech: 1(检测到人声)


3.示例代码
::
    client.RegisterVadObserver(GetVad);
    
    void GetVad(bool isSpeech){
        UnityEngine.Debug.Log("isSpeech"+isSpeech);
    }    

4.出错处理

出错时，函数返回-1。