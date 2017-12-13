SetFileSamplate
==========================
**获取媒体文件数据的采样率**

1.接口说明

获取指定id的媒体文件数据的采样率

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
    int SetFileSamplate(string id, SampleRate samplate)

3.示例代码
::
    client.SetFileSamplate("1", SampleRate::SAMPLERATE_48KHZ);

4.出错处理

出错时，函数返回-1。