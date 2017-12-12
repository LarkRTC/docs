getClient
=============

**创建LarkClient对象**

1.接口说明

使用服务前，先获取LarkClient对象。

2.函数原型
::

    ILarkClient getClient()
    函数返回一个ILarkClient对象，通过该对象的接口来调用后续服务

3.示例代码
::
    
    private ILarkClient client = ClientFactory.getClient(); 


    
