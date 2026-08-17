# IDM 配置文件备份方法

​	有时候我们想用浏览器自带的下载管理器进行下载，但是一点下载却被 IDM 自动嗅探捕获并下载，还有人因为重装系统使得之前更改 IDM 的设置都失效，只得重新再设置一遍，非常地繁琐。其实这两个问题也很好解决。

#### 一、打开 IDM 的下载选项

![](D:\GitHub\Project-Software\疑难解答\assets\IDM配置文件备份方法\v2-cfa5b2e956b02d6a3ad3e0be9dd63ac9_1440w.jpg)

图 ①：打开 IDM 下载选项

​	IDM 使用中会默认启动两个进程。分别是 IDMan.exe、IEMonitor.exe。IDMan.exe 是主程序进程不能关闭，IEMonitor.exe 是监视 IE 内核浏览器点击事件的程序，我们将其关闭即可。

#### 二、在如下对话框中，将勾选的监视基于 IE 内核的浏览器的等事件取消打勾再点击确定即可。

![](D:\GitHub\Project-Software\疑难解答\assets\IDM配置文件备份方法\v2-1d1433e6ac89d2b487e6c86a8c701a71_1440w.jpg)

图 ②：关闭 IDMan.exe

#### 三、对 IDM 设置进行备份

##### （1）一般来说，导致系统重装主要有三个原因。系统运行效率变得低下，垃圾文件充斥硬盘且散乱分布又不便于集中清理和自动清理；系统频繁出错，而故障又不便于准确定位和轻易解决；系统不能启动。因此大家要爱惜电脑，定期进行清理检查哦，否则重装起来特别麻烦。

##### （2）使用快捷键“WIN+S”打开搜索框，点击输入 REGEDIT 运行。

![](D:\GitHub\Project-Software\疑难解答\assets\IDM配置文件备份方法\v2-fb5488da4d5c6b98dc85aa0253bffe69_1440w.jpg)

图 ③：运行 REGEDIT

##### （3）在注册表界面下，找到 DownloadManager 词条，右键将其导出。

![](D:\GitHub\Project-Software\疑难解答\assets\IDM配置文件备份方法\v2-aaa4ec640cf3bc555cd975cc56bfd581_1440w.jpg)


图 ④：导出注册表

##### （4）在对话框中输入保存地址，确定所选分支后点击确定就会自动生成备份，该 [注册表](https://zhida.zhihu.com/search?content_id=148891769&content_type=Article&match_order=3&q=%E6%B3%A8%E5%86%8C%E8%A1%A8&zd_token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJ6aGlkYV9zZXJ2ZXIiLCJleHAiOjE3ODcxMDI3NzYsInEiOiLms6jlhozooagiLCJ6aGlkYV9zb3VyY2UiOiJlbnRpdHkiLCJjb250ZW50X2lkIjoxNDg4OTE3NjksImNvbnRlbnRfdHlwZSI6IkFydGljbGUiLCJtYXRjaF9vcmRlciI6MywiemRfdG9rZW4iOm51bGx9.7Dl_7IPe2EbKOhJ5s8gNfBCbwYkZ1dBcZGYOhLXL9bw&zhida_source=entity) 后缀为.reg, 图示保存在桌面，用户可根据需要选择位置。

  

![](D:\GitHub\Project-Software\疑难解答\assets\IDM配置文件备份方法\v2-5a0c2dddd5b59d75e4161b9648d72f22_1440w.jpg)


图 ⑤：转存注册表

##### （5）重装电脑后，再次打开注册表，右键点击工具栏的文件，选择导入，将备份的文件打开即可。

  

![](D:\GitHub\Project-Software\疑难解答\assets\IDM配置文件备份方法\v2-35c488cbe7f5ca50e43822fa7b435d31_1440w.jpg)


图 ⑥：导入注册表

​	以上便是本期的全部内容，学会备份 IDM 进程设置，就再也不用担心数据失效了。
