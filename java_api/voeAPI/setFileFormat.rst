setFileFormat
===================================
**设置媒体文件数据的位深度**

1.接口说明

设置指定id的媒体文件数据的位深度

2.函数原型
::
    
    int setFileFormat(string id, int[] fmt)

3.示例代码
::
	
    try{
    	int[] format = new int[1];
    	format[1] = 6;
        int tempFmt = client.setFileFormat("1", format);
    } catch (IOException e) {
            e.printStackTrace();
    }

4.出错处理

出错时，函数返回-1。