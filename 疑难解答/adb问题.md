# ADB
1. 配置 ADB 环境方法 ①

   （1）首先下载适用于自己平台的 [Android SDK 平台工具软件](https://developer.android.google.cn/tools/releases/platform-tools?hl=zh-cn)

   （2）解压压缩包，将其中的文件添加到 `C:\Windows\System` 和 `C:\Windows\SysWOW64`

   或者直接将压缩包内的文件解压到这两个路径下面也是可以的




2. 配置 ADB 环境方法 ②

（1）首先下载适用于自己平台的 [Android SDK 平台工具软件](https://developer.android.google.cn/tools/releases/platform-tools?hl=zh-cn)

（2）解压压缩包，将其中的文件解压到任意盘符（C:\  D:\  E:\  F:\……）均可以

（3）右键此电脑→属性→高级系统设置→窗口【系统属性】-高级-环境变量

​	①用户变量→双击`path`→新建[右侧]→输入`%adb%`→确定

​	②系统变量→新建[下方]输入

​		变量名：`adb`
​		变量值：刚解压的文件夹路径	示例：`D:\user\adb\`→确定



3. 柚坛工具箱点击应用管理获取应用列表闪退解决办法

设置 → 系统 → 可选功能 → 相关设置 → 更多 Windows 功能 →

启用以下功能

（.NET Framework 3.5(包括 .NET 2.0 和 3.0)
Windows Communication Foundation HTTP 激活
Windows Communication Foundation 非 HTTP 激活
NET Framework 4.8 Advanced Services

ASP.NET 4.8）而后按照提示确定重启即可



4. 关于卸载应用，加入一个常见错误：DELETE_FAILED_INTERNAL_ERROR

对于卸载内置应用，使用常规的
pm uninstall package_name
会出现错误 DELETE_FAILED_INTERNAL_ERROR，我之前就遇上了好几次，在网上说需要设置--user，正确代码为：
pm uninstall --user 0 package_name



