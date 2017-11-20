createMediaFile
================
**创建播放媒体文件的管道**

1.接口说明

创建一个指定播放模式的媒体文件管道

2.函数原型
::

    int createMediaFile(string path, int mode)

- mode(int):1 单次播放
- mode(int):2 循环播放

3.示例代码
::
    client.CreateMediaFile("///",1);

4.出错处理

出错时，函数返回-1。