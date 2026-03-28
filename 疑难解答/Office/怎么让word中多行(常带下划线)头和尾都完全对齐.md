# 怎么让WORD中多行（常带下划线）头和尾都完全对齐

### ***方法一***：

好文要顶 关注我 收藏该文 微信分享	[雾恋过往](https://home.cnblogs.com/u/2944014083-zhiyu/)  [粉丝 - 5](https://home.cnblogs.com/u/2944014083-zhiyu/followers/) [关注 - 1](https://home.cnblogs.com/u/2944014083-zhiyu/followees/)  

[![](https://pic.cnblogs.com/face/sample_face.gif)](https://home.cnblogs.com/u/2944014083-zhiyu/)

题目如上，写论文的时候封面要写什么题目、班级、学号、指导老师、时间、姓名一堆东西。大概如下所示；

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200521184536849.png#pic_center)

&nbsp;       问题的关键在于出现数字的哪一行总是对不齐，当然，是后面对不齐，前面一般用空格都能对齐，上面这张图是我改过对齐的，给你看看对不齐是啥样的。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200521184949821.png#pic_center)  
        看到没有，2016级哪儿明显出来了一个尾巴，而且不管我们怎么打空格都对不齐。怎么办呢，找了很多办法都没有说这个问题的。

&nbsp;       自己搞出来了两个方法和一个我解决不了问题我就解决提出问题的人，介绍第一个，也是我最喜欢用的。首先打开word里面的 **显示/隐藏编辑标记**，目的就是想显示空格、制表符、回车这东西。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200521185725327.png#pic_center)

&nbsp;       打开后是这样的

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200521185822539.png#pic_center)  
        然后我们开始操作，首先光标定在任意位置右键打开段落，打开后找到左下角制表位  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200521190146219.png#pic_center)  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200521190316281.png#pic_center)  
                1、输入一个数字大一点，比如22

&nbsp;               2、点右对齐

&nbsp;               3、设置

&nbsp;               4、确定

&nbsp;       然后把光标定在在每一行的最后位置，点下tab键（q左边那个），每一行都这样处理，就Ok了。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200521190613860.png#pic_center)

&nbsp;       隐藏编辑标记后，长这样，和第一张效果图一样

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200521190721886.png#pic_center)

&nbsp;       第一种方法介绍完了，主要就是利用tab键来搞定，

&nbsp;       第二种方法我不细说，没图演示了，我们用word画一根横线，每一行都复制这根横线，不就保证下划线长度一样了吗，哈哈哈，至于怎么使横线像下划线，你改文字环绕方式不就好了，什么浮于文字上方，衬于文字下方啥的。

&nbsp;       这太low了，我虽然试过，但不想用，只给提供思路。

&nbsp;       还有的就是我解决不了问题我可以解决提出问题的人呀。这个东西我文字形式搞不定，我用表格，然后表格边框我只显示后面的不就好了，或者我直接把他当图，在Visio里面画好图把他粘贴过来不也可以吗？

这两种我都用过，都是可以的，用表的话会稍稍麻烦一些，你最好对表格的一些处理比较熟悉。

### *方法二*：

最新推荐文章于 2025-11-04 12:19:58 发布	原创 于 2018-03-17 13:17:49 发布 · 4.5w 阅读

​	CC 4.0 BY-SA版权_版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。

 [![](https://i-blog.csdnimg.cn/columns/default/20201014180756724.png?x-oss-process=image/resize,m_fixed,h_224,w_224) 经验技巧 专栏收录该内容](https://blog.csdn.net/icurious/category_7265263.html "经验技巧")

## 『如何』让WORD中多行（常带下划线）头和尾都完全对齐

> “为啥Word多行下划线后面总是长短不一，无论怎么调不是多了就是少了？怎样才能完美对齐呢？”

![](https://i-blog.csdnimg.cn/blog_migrate/39e69dccaf933d86aa1f9c8bc7001860.webp?x-image-process=image/format,png)

* * *

### 通过本文你可以

1.  如何对齐Word中的多行文本，达到可以容忍的地步（基础级别）；
2.  知道为什么对不齐的原因；
3.  学会Word中对于段落的常用操作；
4.  如何对齐Word中的多行文本，达到肉眼无法识别的地步（死磕级别）；

* * *

### 为什么是Word？为什么要对齐？

虽然很多大佬在电脑上创作时，已经放弃使用Word而使用诸如`jupyter notebook`，`Sublime Text`，甚至更专业的`Latex`。但很多场合下，填写一些表格材料，撰写一些报告，依然还会需要用到Word来作为得力的办公助手。作为一个处（强）女（迫）座（症）追求足够好的魔法师，怎么能容忍自己还有别人递交的表格出现上下两行下划线停在不同地方的行为！？

比如说这样：  
![不整齐的效果](https://i-blog.csdnimg.cn/blog_migrate/da642ad05e1a017cc826d98199c6fba3.webp?x-image-process=image/format,png)

除了横线是直的，其余各处都没有做到相应的对齐，比如没一样的左对齐（1），或者填写项目的对齐（2），或者填写内容中间点的对齐（3），最后也同样重要的每一行最末端的对齐（4）。

对不对齐就问题本身而言是小事，我们要看重内涵，即所书写的内容是什么。但是，假如在保证内容质量的前提下，保证形式上的美观得体，对于其他人而言是一种享受，对于自己做事情的态度也是一种历练。

这里魔法师本人无意就排版和对齐问题做过多的讨论，有更专业的人，比如前端工程师，新媒体运营等会提供更专业的指点和精细到无以复加的研究和实践，通过本人的实践，对于该问题，给出两种程度的解决方案，前者能达到效果足够好（把word文档放大到150%以上会看到细微不整齐），后一种可以达到放大后依然没有普通肉眼可见的不整齐的情况。闲言碎语不多讲，下面开始。

* * *

### 怎么哪里不整齐？为什么不整齐？

这还不简单，用眼睛看呗！恭喜你，答对了！

我这里给出一点小技巧：除了用眼睛直观地看，当你觉得某几行有问题的时候，使用鼠标或者键盘对这几行进行选择，这时候就很容易观察到哪里不整齐了。

![](https://i-blog.csdnimg.cn/blog_migrate/bb0299c0f67fcecf243eb5adc03afa37.webp?x-image-process=image/format,png)

那么问题来了，为什么会不整齐呢？

我自己的结论是：**制作这些文档的人技术太烂**，很多时候就是这个原因，你拿到一张需要填写的文档时，在什么有没有填写的情况下，**本来它就没有被制作文档的人排列整齐**！很多文档的段落缩进都是制作的人使用狂按空格键弄出来的，大差不差就行了，根本没有设置段落缩进。

还有情况就是，文档的版式没问题，缩进没问题，段落也是对齐的。但是你填写了点东西后，**本来整齐的地方怎么调也调不整齐了**。

比如说下面这样：

想对齐，增加一个空格，发现多了一点，

![增加.png](https://i-blog.csdnimg.cn/blog_migrate/0a0932e0fd38096ccf9b89825c9775b9.webp?x-image-process=image/format,png)

删除一个空格，发现又短了一截：

![减少.png](https://i-blog.csdnimg.cn/blog_migrate/20c69f7ce6e7cd066cfd4ba02b539c61.webp?x-image-process=image/format,png)

这就相当的尴尬了，毫无疑问，不是增减空格能够解决的，本质是格式设置上的原因。

* * *

### 解决办法

#### 足够好的方法

* 首先，判断是否是文档本身不齐的导致的：选定打算对齐的几行；
* 选择“开始”->“段落”（或者鼠标右键，“段落”）

![段落.png](https://i-blog.csdnimg.cn/blog_migrate/89547b4369ffdc4fa41a20841d108af3.webp?x-image-process=image/format,png)

* 调整对齐方式和缩进，选择两端对齐和对称缩进；
* 必要情况下调整缩进的内外值，注意下方的预览；

以上可以很容易解决大部分的对齐问题，并且整个多行，你想将其**保持居左对齐的前提下，移动到文档中间的某个位置**，不建议使用`Tap`键，同样在这里进行设置也就行了。

#### 更好的方法

这种方法针对填写了东西后，无法对齐，以及喜欢死磕怎么整齐都不为过的情况。

有时候你觉得效果已经最够好了，但其实放大之后，依然不是那么的完美。例如下发：

![](https://i-blog.csdnimg.cn/blog_migrate/3562b5241b6013d7adc28ec0503f7e5b.webp?x-image-process=image/format,png)

观察和解决步骤如下：

* 打开标记（图中的小点点点和回车符号等）：快捷键`ctrl+*`或者”段落”->”打开隐藏编辑标记”  
    ![](https://i-blog.csdnimg.cn/blog_migrate/9a739830c5b266b8a56492fb898c641b.webp?x-image-process=image/format,png)
    
* 和上面一种方法一样，修改段落缩进和对齐方式，增加/删除空格查看对齐效果
  
* 如果效果不理想，说明是和你输入的内容有关：设置统一输入的中文，英文，数字等的字体等属性  
    ![](https://i-blog.csdnimg.cn/blog_migrate/e7bf164f9e9405f90be857387431a1c2.webp?x-image-process=image/format,png)

![](https://i-blog.csdnimg.cn/blog_migrate/5d9785272ca7d08cf6658ed9823c077e.webp?x-image-process=image/format,png)

* 加入还是不理线：这只段落缩进，进行微调

![](https://i-blog.csdnimg.cn/blog_migrate/1bc2d4c9557d771d82ba38c2afdf6498.webp?x-image-process=image/format,png)

一直到达理想的效果为止。

最终的效果：

![对齐的效果](https://i-blog.csdnimg.cn/blog_migrate/08bfea6315b374e0af216cd4ea12c582.webp?x-image-process=image/format,png)

是不是很Amazing，非常整齐。

> PS: 最后，对于史蒂芬·霍金先生的敬意和纪念。
> 
> I would like to show my respect to Stephen Hawking.