3dPositionSetting 3d音效的位置设置
=========================================

**3d音效的位置设置**

1.接口说明

位置设置(以下API都需要在调用enable3DVoice之后设置，setSpeakerPosition需要在创建相应channel之后才能调用成功)

2.函数原型
::
   int setListenerPosition(float x, float y, float z)//设置自己的空间位置

   int setFaceVector(float x, float y, float z)//设置自己前方的方向向量

   int setUpVector(float x, float y, float z)//设置自己头顶的方向向量

   int setSpeakerPosition(string id, float x, float y, float z) //设置指定id的说话人的空间位置

3.示例代码
::

   client.setFaceVector(0, 1, 0);
   client.setListenerPosition(0, 0, 0);
   client.setUpVector(0, 0, 1);
   client.setSpeakerPosition("1", 2, 0, 0)

4.出错处理

出错时，函数返回-1。
