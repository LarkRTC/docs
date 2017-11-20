SetStreamVoicePcmFormat
=========================
**设置流式文件数据的位深度**

1.接口说明

设置指定id的系统音效数据的位深度

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
    int SetStreamVoicePcmFormat(string id, Format fmt)

3.示例代码
::
    client.SetStreamVoicePcmFormat("1",Format::FORMAT_S16);

4.出错处理

出错时，函数返回-1。