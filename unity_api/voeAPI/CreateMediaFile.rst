CreateMediaFile
================
**创建播放媒体文件的管道**

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
    client.CreateMediaFile("///",MediaFileMode.MOCE);

4.出错处理

出错时，函数返回-1。