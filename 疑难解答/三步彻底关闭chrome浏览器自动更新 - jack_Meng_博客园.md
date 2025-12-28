# [三步彻底关闭chrome谷歌浏览器自动更新](https://www.cnblogs.com/mq0036/p/13947021.html "发布于 2020-11-09 09:43")

不想让Chrome浏览器自动更新，主要是因每个人可能都不一样。看了网上的很多方法都不管用，后来找到这个方法测试成功后真的太开心了。现在分享给大家，希望给需要的人一点帮助吧。

不知道是不是Win10系统的原因，以前试过改注册表的方式，不过失败了，而且改注册表这种作死的事感觉有点复杂，也有点不安，最后找到了更加简单有效的方法，在这里记录一下。

&nbsp;

## 第一步：禁用任务计划

首先是【右键计算机->管理】，在【计算机管理(本地)->系统工具->任务计划程序->任务计划程序库】中找到两个和Google自动更新相关的任务计划【GoogleUpdateTaskMachineCore】与【GoogleUpdateTaskMachineUA】，并把它俩禁用掉。印象中介绍这方法的网游的截图里是有三个任务计划的，我这边只有俩，如果有多个的话就发挥自己的聪明才智判断一下是否是和Chrome的自动更新相关的吧~

![](https://img2020.cnblogs.com/blog/256716/202011/256716-20201109093731401-1701509123.png)

&nbsp; 

## 第二步：禁用更新服务

然后在下方的【服务和应用程序->服务】中，找到两个和Google更新相关的服务【Google更新服务(gupdate)】、【Google更新服务(gupdatem)】，并右键，选择属性，把启动类型改为禁用。如果没有找到的可以略过。

![](https://img2020.cnblogs.com/blog/256716/202011/256716-20201109093916459-837759389.png)

&nbsp;

##  第三步：重命名更新程序

完成上面两步后理论上就可以停止Chrome的自动更新了，不过有网友说这么做之后，**不要在Chrome中点击**【帮助->关于Google Chrome】。我是没有作死过，不过既然有人这么说了，那就最好不要点了吧~

但是越说不让点有的小伙伴就是越想点，以往各种方法禁用chrome自动升级不成功，它有各种方法来升级谷歌，但一定是使用update里的升级程序来升级的，你可重命名或删除里面的文件，但是它会直接生成，在来Update文件夹上右键，在属性里的安全页签里点击编辑，设置system完全控制权设置为拒绝，administrator权限也是它赋予的。System是最高权限，设置完了之后google就没有权限动这个文件了。我们切断这一步，只要它没法在里面生成程序，那么它就无法升级了。

默认路径:C:\\Users\\Administrator\\AppData\\Local\\Google\\Chrome\\Application\\chrome.exe

另外有看到另外的一个方法更加简单，就是在C盘中把GoogleUpdate.exe文件改个名~这个是Chrome默认的安装位置（应该），如果你用过什么黑科技改过安装位置的话，按照相对路径来找吧，应该大同小异。

![](https://img2020.cnblogs.com/blog/256716/202011/256716-20201109100749681-1365750689.png)

&nbsp;我自己的使用的是默认路径，如下图：

![](https://img2020.cnblogs.com/blog/256716/202011/256716-20201109094110828-1883584848.png)

 

这个方法感觉还是很李菊福的。至于如果只改GoogleUpdate.exe文件的文件名，而不在管理中禁用任务计划和服务有没有效果的话，我……没试过~窝反正上面三步都做了，现在Chrome就算点进去关于界面也不会自动更新了。推荐勇敢的少年去试试，我的推理是应该是可以只改文件名的。

<br/><br/>出处：https://www.jianshu.com/p/6c5323a880d0

参考：https://blog.csdn.net/yexiaomodemo/article/details/102993720

\=======================================================================================

# 彻底关闭Chrome浏览器自动更新

一、在服务中禁用Google更新

![](https://img-blog.csdnimg.cn/31950b907e81431a80449b2c0cd2a382.png)

二、Chrome更新是利用update里的升级程序来升级的，所以可以删除里面的文件。但是如果直接删除Chrome又会自动生成。所以可以考虑切断这一步，只要Chrome没法在Update文件夹里生成更新程序，那么Chrome就无法升级了。

所以首先清空Update文件夹并设置权限，让Chrome没有权限修改这个文件夹。

删除C:\\Program Files (x86)\\Google\\Update目录中的所有内容

![](https://img-blog.csdnimg.cn/8ac787ba697e4f929fe322a5b314a3ee.png)

然后右键Update文件夹，打开属性，点击“安全”选项卡，System完全控制权设置为拒绝。System是最高权限，设置完了之后Chrome就没有权限动这个文件了。 

![](https://img-blog.csdnimg.cn/6bba5d5df29d45cc845552920ae3a420.png) 

![](https://img-blog.csdnimg.cn/ac551b22859141ef972feefaf80bc1dd.png)

至此，Chrome就能永久禁止更新了。

三、Chrome浏览器自动更新失败右上角会有弹窗提示

![](https://img-blog.csdnimg.cn/ccb7e05ef50b4e78818b0349119b50d3.png)  
关闭弹窗的话需要右键chrome应用程序，选择属性，在目标选项的末尾输入

> &nbsp;--disable-background-networking

然后应用，确定，重启即可。

![](https://img-blog.csdnimg.cn/02ccd5fb48ee46b3b93c673ee8c37d33.png)

【注意】如果Chrome浏览器固定在任务栏，需要从任务栏取消固定，然后把上面操作好的重新固定在任务栏就行。

出处：https://blog.csdn.net/weixin_37858453/article/details/126600461
