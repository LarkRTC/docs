setFileChannelNum
===============================
**设置媒体文件数据的声道数**

1.接口说明

设置指定id的媒体文件数据的声道数

2.函数原型
::

    int setFileChannelNum(String id,int[] channelNum)

3.示例代码
::
    try{
    	int[] channelNum = new int[1];
    	channelNum[0] = 2;
        int tempChannelNum = client.setFileChannelNum("1", channelNum);
    } catch (IOException e) {
            e.printStackTrace();
    }
    
4.出错处理

出错时，函数返回-1。