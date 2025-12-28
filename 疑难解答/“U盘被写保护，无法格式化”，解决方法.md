# U盘插入电脑说要格式化，但电脑又说“磁盘被写保护，无法格式化”，如何解决

原创 已于 2023-08-13 09:28:36 	修改 · 1.7w 阅读

​	CC 4.0 BY-SA版权	本文为博主原创文章，未经博主允许不得转载。

​	于 2022-10-28 09:52:27 首次发布

## 错误描述

用balenaetcher刻录过系统镜像，但是想重新刻录其他的系统镜像，发现插入u盘之后看不到文件，也没法格式化，说有写保护。  
在这里也无法格式化磁盘：  
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/0a38a5f18fb5555dc25020a61bddc440.png)  
直接格式化磁盘，提示有写保护。  
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/5849106f5016820349584dde24b64570.png)

## 解决方法

步骤：

* 1、win+r
* 2、输入 cmd 回车
* 3、输入 diskpart 回车
* 4、输入 list disk 回车
* 5、输入 select disk n(这里的n是数字，指的是你u盘的编号，从磁盘大小上能判断那个是你的u盘) 回车
* 6、输入 clean 回车
* 7、输入 create partition primary 回车

![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/22c0d47eaea13efb745c0463f1b846c8.png)  
然后就可以格式化U盘了。  
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/cb053e924b28ece6fa614ef30674c318.png)  