setStreamVoicePcmSamplate
==========================
**设置流式文件数据的采样率**

1.接口说明

设置指定id的系统音效数据的采样率

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
    int setStreamVoicePcmSamplate(String id, int[] sampleRate)

3.示例代码
::

    try{
    	int[] sampleRate = new int[1];
    	sampleRate[0] = 48000;
        int tempSamplate = client.setStreamVoicePcmSamplate("1", sampleRate);
    } catch (IOException e) {
            e.printStackTrace();
    }

4.出错处理

出错时，函数返回-1。