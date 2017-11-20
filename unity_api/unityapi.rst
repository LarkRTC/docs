Unity3d API
===========

**1.概述**

初始化需要依次调用初始化引擎，注册服务器。
初始化完成后通过StartSpeak，StopSpeak，StartListen和StopListen来控制连麦。

**2.API调用方法**

**2.1 创建LarkClient对象**

1.接口说明

使用服务前，先获取LarkClient对象。

2.函数原型
::

    ILarkClient GetLarkClient()
    改函数返回一个ILarkClient对象，通过该对象的接口来调用后续服务

3.示例代码
::
    
    private ILarkClient client = LarkClientFactory.GetLarkClient(); 


**2.2 初始化音频引擎**

1.接口说明

初始化音频引擎，需在初始化环境之后，调用其他函数前进行调用。
初始化之后即可使用本地录音功能，本地文件流播放，本地文件播放功能。

2.函数原型
::

    int Init();

3.示例代码
::
    
    client.Init();

4.出错处理

出错时，函数返回-1，一般是因为硬件的录音播放设备或者权限有问题

**2.3 销毁音频引擎**

1.接口说明

销毁音频引擎坏境。

2.函数原型
::
    
    void Destroy();

3.示例代码
::
    
    client.Destroy();

**2.4 音频服务注册**

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
mode       string      | mode设计分为主播模式（mode=1）和听众模式（mode=2),       
                       | 听众只能收听语音不能发送语音，而主播既可以发送语音也可以收听语音        
roomID     string      | 房间ID,只有相同房间的人才能进行互相通讯                                 
======== =========== ========================================================================= 


3.示例代码
::
    
    client.Register("fef68f5cf1a1ad61", "95dc07bda45acba098b83f8ed29e460d", "1", 1, "1");

4.出错处理

出错时，函数返回-1。

**2.5 注销音频服务**

1.接口说明

断开和服务器的连接，使用本地模式。

2.函数原型
::

    int DeRegister();

3.示例代码
::
    
    client.DeRegister();

4.出错处理

出错时，函数返回-1。

**2.6 开始说话**

1.接口说明

开始说话，开启自己的麦克风，所有listen的人都能听见此端语音

2.函数原型
::

    int StartSpeak();

3.示例代码
::
    
    client.StartSpeak();

4.出错处理

出错时，函数返回-1。

**2.7 停止说话**

1.接口说明

停止说话，关闭自己的麦克风，不让别人听到此端的语音。

2.函数原型
::

    int StopSpeak();

3.示例代码
::
    
    client.StopSpeak();

4.出错处理

出错时，函数返回-1。

**2.8 创建声音管道**

1.接口说明

创建和指定id(想要听的人)的声音管道，初始化管道环境。

2.函数原型
::

    int CreateChannel(string id);

3.示例代码
::
    
    client.CreateChannel("1");

4.出错处理

出错时，函数返回-1。


**2.9 销毁声音管道**

1.接口说明

删除和指定id(想要听的人)的声音管道，销毁管道环境。

2.函数原型
::

    int DeleteChannel(string id);

3.示例代码
::
    
    client.DeleteChannel("1");

4.出错处理

出错时，函数返回-1。

**2.10 开始听某人声音**

1.接口说明

(需要先调用CreateChannel创建管道)听别人说话，id即为对方register时传递的userID，必须保证双方的APPID与ROOMID相同才能互相连麦。

2.函数原型
::

    int StartListen(string id);

3.示例代码
::
    
    client.StartListen("1");

4.出错处理

出错时，函数返回-1。

**2.11 停止听某人声音**

1.接口说明

(停止后可调用DeleteChannel删除管道,用于释放资源)停止听对方说话，id为对方register时传递的userID。

2.函数原型
::

    int StopListen(string id);

3.示例代码
::
    
    client.StopListen("1");

4.出错处理

出错时，函数返回-1。


**2.12 开启语音消息录制**

1.接口说明

开始录制语音消息，需要先调用Init函数之后调用该函数。(可以本地录音，无需联网)语音数据可在注册的回调中获得。

2.函数原型
::

    int StartRecordVoiceData();

3.示例代码
::
    
    client.StartRecordVoiceData();

4.出错处理

出错时，函数返回-1。



**2.13 停止语音消息录制**

1.接口说明

停止录制语音消息。

2.函数原型
::

    int StopRecordVoiceData();

3.示例代码
::
    
    client.StopRecordVoiceData();

4.出错处理

出错时，函数返回-1。


**2.14 获取录制声音数据的位深度**

1.接口说明

录音数据的位深度信息

2.函数原型
::
	enum Format
    {
        FORMAT_U8 = 0,          //< unsigned 8 bits
        FORMAT_S16 = 1,         //< signed 16 bits
        FORMAT_S32 = 2,         //< signed 32 bits
        FORMAT_FLT = 3,         //< float
        FORMAT_DBL = 4,         //< double
        FORMAT_U8P = 5,         //< unsigned 8 bits, planar
        FORMAT_S16P = 6,        //< signed 16 bits, planar
        FORMAT_S32P = 7,        //< signed 32 bits, planar
        FORMAT_FLTP = 8,        //< float, planar
        FORMAT_DBLP = 9,       //< double, planar
    }
    int GetRecordVoiceDataFormat(Format &fmt)

3.示例代码
::
    Format tempFmt;
    client.GetRecordVoiceDataFormat(tempFmt);

4.出错处理

出错时，函数返回-1。

**2.15 获取录制声音数据的声道**

1.接口说明

录音数据的位深度信息

2.函数原型
::
	
    int GetRecordVoiceChannelNum(uint32 &channelNum)

3.示例代码
::
    uin32_t tempChannelNum = 0;
    client.GetRecordVoiceChannelNum(tempChannelNum);

4.出错处理

出错时，函数返回-1。

**2.16 获取录制声音数据的采样点个数**

1.接口说明

录音数据的最大采样点个数

2.函数原型
::
	
    int GetRecordVoiceMaxSamplateCount(uint32_t &maxSamplateCount)

3.示例代码
::
    uint32_t tempSamplateCounts = 0;
    client.GetRecordVoiceMaxSamplateCount(tempSamplateCounts);

4.出错处理

出错时，函数返回-1。

**2.17 创建流式文件播放管道**

1.接口说明

创建一个用于播放流式系统音效的channel

2.函数原型
::
	
    int CreateStreamVoiceChannel(string id, NeedMoreAudioDataCallback needAudio)

    int NeedMoreAudioDataCallback:(void*)( string id, IntPtr data, ushort sampleNums, uint channelNum)
    该回调函数每10ms会抛出,请求播放指定采样率,声道数,位深度配置的数据,
    如果数据不合要求，播放会失败.用户可以在该回调函数中给data赋值即可达到播放效果.


- 回调函数参数说明：

=========== ============ ====================================
参数          类型          说明                             
=========== ============ ====================================
id           string       创建的系统音效管道id          
data         IntPtr       需要播放的pcm数据              
sampleNums   ushort       需要播放的采样点的个数      
channelNum   string       需要播放的声道数(只支持单双声道) 
=========== ============ ====================================

3.示例代码
::
    _client.CreateStreamVoiceChannel("streamChannel", PushSysVoiceData);
    void PushSysVoiceData(string id, IntPtr data, ushort sampleNums, uint channelNum)
    {
        byte[] buf = reader.ReadBytes((int)(sampleNums * channelNum * 2));
        if (buf.Length <= 0)
        {
            return;
        }
        Marshal.Copy(buf, 0, data, (int)(sampleNums * channelNum * 2));
    }
**数据位深度等信息可以先调用以下get函数获取支持的配置**

4.出错处理

出错时，函数返回-1。

**2.18 删除流式文件播放管道**

1.接口说明

删除一个用于播放流式系统音效的channel

2.函数原型
::
	
    int DeleteStreamVoiceChannelstring(string id)

3.示例代码
::
    client.DeleteStreamVoiceChannelstring("streamChannel");

4.出错处理

出错时，函数返回-1。

**2.19 获取流式文件数据的位深度**

1.接口说明

获取指定id的系统音效数据的位深度

2.函数原型
::
 enum Format
    {
        FORMAT_U8 = 0,          //< unsigned 8 bits
        FORMAT_S16 = 1,         //< signed 16 bits
        FORMAT_S32 = 2,         //< signed 32 bits
        FORMAT_FLT = 3,         //< float
        FORMAT_DBL = 4,         //< double
        FORMAT_U8P = 5,         //< unsigned 8 bits, planar
        FORMAT_S16P = 6,        //< signed 16 bits, planar
        FORMAT_S32P = 7,        //< signed 32 bits, planar
        FORMAT_FLTP = 8,        //< float, planar
        FORMAT_DBLP = 9,       //< double, planar
    }
    int GetStreamVoicePcmFormat(string id, Format &fmt)

3.示例代码
::
    Format tempFmt;
    client.GetStreamVoicePcmFormat("1",tempFmt);

4.出错处理

出错时，函数返回-1。

**2.20 获取流式文件数据的声道数**

1.接口说明

获取指定id的系统音效数据的声道数

2.函数原型
::
    enum ChannelFormat
    {
        MONO = 1,       //< 1 channel
        STEREO = 2,     //< 2 channels
    };
    int GetRecordVoiceChannelNum(ChannelFormat &channelNum)

3.示例代码
::
    ChannelFormat tempChannelNum;
    client.GetStreamVoicePcmChannelFormat("1",tempChannelNum);

4.出错处理

出错时，函数返回-1。

**2.21 获取流式文件数据的采样率**

1.接口说明

获取指定id的系统音效数据的采样率

2.函数原型
::
    enum SampleRate
    {

        SAMPLERATE_8KHZ = 8000,
        SAMPLERATE_16KHZ = 16000,
        SAMPLERATE_32KHZ = 32000,
        SAMPLERATE_48KHZ = 48000,
        SAMPLERATE_96KHZ = 96000,
        SAMPLERATE_441KHZ = 44100,
        SAMPLERATE_12KHZ = 12000,
        SAMPLERATE_24KHZ = 24000,
    };
    int GetRecordVoiceMaxSamplateCount(SampleRate &samplate)

3.示例代码
::
    SampleRate tempSamplate;
    client.GetRecordVoiceMaxSamplateCount("1", tempSamplate);

4.出错处理

出错时，函数返回-1。

**2.22 创建播放媒体文件的管道**

1.接口说明

创建一个指定播放模式的媒体文件管道

2.函数原型
::
    enum MediaFileMode
    {
        MODE_ONCE = 1,
        MODE_LOOP = 2,
    }
    int CreateMediaFile(string path, MediaFileMode mode)

3.示例代码
::
    ChannelFormat tempChannelNum;
    client.CreateMediaFile("///",MediaFileMode.MOCE);

4.出错处理

出错时，函数返回-1。

**2.23 开始播放媒体文件**

1.接口说明

开始播放文件

2.函数原型
::
    int StartPlayMediaFile(string path)

3.示例代码
::
    client.StartPlayMediaFile("///");

4.出错处理

出错时，函数返回-1。

**2.24 停止播放媒体文件**

1.接口说明

开始播放文件

2.函数原型
::
    int StopPlayMediaFile(string path)

3.示例代码
::
    client.StopPlayMediaFile("///");

4.出错处理

出错时，函数返回-1。

**2.25 3d音效开关**

1.接口说明

3d音效开关，默认对于所有听取的用户生效
播放文件时最好是在播放前设置好是否开启3d音效

2.函数原型
::
    int Enable3DVoice(bool open)

3.示例代码
::
    client.Enable3DVoice(true);

4.出错处理

出错时，函数返回-1。

**2.26 3d音效的位置设置**

1.接口说明

位置设置

2.函数原型
::
   int SetListenerPosition(float x, float y, float z)//设置自己的空间位置

   int SetFaceVector(float x, float y, float z)//设置自己前方的方向向量

   int SetUpVector(float x, float y, float z)//设置自己头顶的方向向量

   int SetSpeakerPosition(string id, float x, float y, float z) //设置指定id的说话人的空间位置

3.示例代码
::

   client.SetFaceVector(0, 1, 0);
   client.SetListenerPosition(0, 0, 0);
   client.SetUpVector(0, 0, 1);
   client.SetSpeakerPosition("1", 2, 0, 0)

4.出错处理

出错时，函数返回-1。

**3.回调API**

**3.1注册网络错误回调**

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
         UnityEngine.Debug.Log("Net Error");
    }    

4.出错处理

出错时，函数返回-1。

**3.2 网络注册是否成功回调**

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

**3.3 注册语音消息录制回调**

1.接口说明

注册语音录制消息回调，调用StartRecordVoiceData函数之后就会抛出该回调事件来抛出声音数据

2.函数原型
::
    int RegisterRecordPcmData(RecordPcmVoiceData  recordData)
    RecordPcmVoiceData :(void*)(byte[] data, ushort dataLen)

**[录音数据的具体参数(采样率，位深度，声道数)可以通过相关的Get函数获取**

3.示例代码
::
    client.RegisterRecordPcmData(RecordData);
    void RecordData(byte[] data, ushort dataLen){

    }    

4.出错处理

出错时，函数返回-1。

**3.4 注册静音检测回调**

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