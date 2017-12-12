SDK用法
=======

**注册**
使用LarkVoiceEngine需要先注册账号，登录 dashboard_ (https://dashboard.larkrtc.com/) 注册账号。
应用管理中创建应用，复制应用对应的APPID和APPKEY，调用API时填入相应的字符串。

**集成**
下载对应版本的SDK。
Android SDK，将AAR放到项目的app/libs目录下，app/build.gradle中dependency加入compile(name:'lark-native', ext:'aar')
Unity SDK，打开待集成项目，菜单Assets->ImportPackage->CustomPackage..., 选择下载的UnityPackage，全部导入即可。

**使用**
API使用方法详见API文档。


Demo:

| unityDemo_
| javaDemo_

.. _dashboard: https://dashboard.larkrtc.com/

.. _unityDemo: http://www.baidu.com/

.. _javaDemo: http://www.baidu.com/