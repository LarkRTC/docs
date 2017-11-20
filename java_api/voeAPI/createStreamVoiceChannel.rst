createStreamVoiceChannel
=========================
**创建流式文件播放管道**

1.接口说明

创建一个用于播放流式系统音效的channel

2.函数原型
::
	
    int createStreamVoiceChannel(String id, INeedAudio needAudio)

    int INeedAudio:(void*)(final String id, byte[] data, int sampleNums, int channelNum);
    该回调函数每10ms会抛出,请求播放指定采样率,声道数,位深度配置的数据,
    如果数据不合要求，播放会失败.用户可以在该回调函数中给data赋值即可达到播放效果.


- 回调函数参数说明：

=========== ============ ====================================
参数          类型          说明                             
=========== ============ ====================================
id           String       创建的系统音效管道id          
data         byte[]       需要播放的pcm数据              
sampleNums   int          需要播放的采样点的个数      
channelNum   int          需要播放的声道数(只支持单双声道) 
=========== ============ ====================================

3.示例代码
::
    client.createStreamVoiceChannel("streamChannel", this);
    void needAudio(final String id, byte[] data, int sampleNums, int channelNum);
    {
        int realByteCounts =0;
        try {
            realByteCounts = in.read(data);
        } catch (IOException e) {
            e.printStackTrace();
        }

        if(0 !=realByteCounts){
            System.arraycopy(data, 0, bytes, 0, realByteCounts);
        }
    }

**数据位深度等信息可以先调用以下get函数获取支持的配置**

4.出错处理

出错时，函数返回-1。