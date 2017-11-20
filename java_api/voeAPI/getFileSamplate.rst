getFileSamplate
==========================
**获取媒体文件数据的采样率**

1.接口说明

获取指定id的媒体文件数据的采样率

2.函数原型
::
    
    int getFileSamplate(String id)

3.示例代码
::

    try{
        int tempSamplate = client.getFileSamplate("1");
    } catch (IOException e) {
            e.printStackTrace();
    }

4.出错处理

出错时，函数返回-1。