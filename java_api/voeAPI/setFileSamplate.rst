setFileSamplate
==========================
**设置媒体文件数据的采样率**

1.接口说明

设置指定id的媒体文件数据的采样率

2.函数原型
::
    
    int setFileSamplate(String idm int[] sampleRate)

3.示例代码
::

    try{
    	int[] sampleRate = new int[1];
    	sampleRate[0] = 48000;
        int tempSamplate = client.setFileSamplate("1", sampleRate);
    } catch (IOException e) {
            e.printStackTrace();
    }

4.出错处理

出错时，函数返回-1。