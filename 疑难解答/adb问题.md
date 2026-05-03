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



3. 华为用有线ADB开启无线调试办法(提前在电脑上配置好ADB环境)

   > ①以管理员身份运行`cmd` 或者`power shell`
   >
   > ②打开手机`开发者模式`(连续点7次版本号，输入密码即可)，进入开发者模式(*系统和更新→开发人员选项→打开 "仅充电"模式下允许ADB调试、USB调试*)
   >
   > ③找一条**带数据传输功能**的手机充电线，连接手机和电脑
   >
   > ④USB 连接方式 选择 `仅充电`，点击复选框`☑ 始终允许使用这台计算机进行调试`，点击确定
   >
   > ⑤在电脑`cmd`或者`power shell`中
   >
   > 1. 输入`adb devices`，出现设备
   >
   > `List of devices attached`
   > `XXXXXXXXXXXXXXXX	device`
   >
   > 即可
   >
   > 2. 接着输入`adb tcpip 5555`出现
   >
   > `restarting in TCP mode port：5555`
   >
   > 即可
   >
   > ⑥拔掉数据线，在手机shizuku中点击无线调试启动→5555
   >
   > 等待出现下列提示即可
   >
   > Service started, this window will be automatically
   > closed in 3 seconds
   >
   > ⑦完成调试



4. 柚坛工具箱点击应用管理获取应用列表闪退解决办法

设置 → 系统 → 可选功能 → 相关设置 → 更多 Windows 功能 →

启用以下功能

（.NET Framework 3.5(包括 .NET 2.0 和 3.0)
Windows Communication Foundation HTTP 激活
Windows Communication Foundation 非 HTTP 激活
NET Framework 4.8 Advanced Services

ASP.NET 4.8）而后按照提示确定重启即可



5. 关于卸载应用，加入一个常见错误：DELETE_FAILED_INTERNAL_ERROR

对于卸载内置应用，使用常规的
pm uninstall package_name
会出现错误 DELETE_FAILED_INTERNAL_ERROR，我之前就遇上了好几次，在网上说需要设置--user，正确代码为：
pm uninstall --user 0 package_name

