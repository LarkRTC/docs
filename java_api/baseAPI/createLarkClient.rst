createLarkClient 创建引擎对象
===================================

**创建LarkClient对象**

1.接口说明

使用服务前，先获取LarkClient对象。

2.函数原型
::
    ILarkClient LarkClientFactory.createLarkClient();

函数返回一个ILarkClient对象，该对象是Lark引擎的基础对象，通过该对象的接口来调用后续服务.

3.示例代码
::    
    private ILarkClient client = LarkClientFactory.createLarkClient();


    
