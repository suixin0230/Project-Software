对于 Win11/10 操作系统绑定了微软账号的用户，要求通过输入账号密码或 PIN 码进行登录。如果忘记密码或根本不知道密码怎么办呢？这个问题很容易解决，即便是小白也一看就会，下面给大家介绍一下方法。

![](./assets/绕过Windows微软账户登录和密码清除/0.jpg)

一、准备条件

① [WinPE](https://zhida.zhihu.com/search?content_id=240051295&content_type=Article&match_order=1&q=WinPE&zd_token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJ6aGlkYV9zZXJ2ZXIiLCJleHAiOjE3Nzk3NzkwODUsInEiOiJXaW5QRSIsInpoaWRhX3NvdXJjZSI6ImVudGl0eSIsImNvbnRlbnRfaWQiOjI0MDA1MTI5NSwiY29udGVudF90eXBlIjoiQXJ0aWNsZSIsIm1hdGNoX29yZGVyIjoxLCJ6ZF90b2tlbiI6bnVsbH0.cpkcHW7erIsi2Yngxx0uICzUO6xPLSf99pev5IhvdSQ&zhida_source=entity)，随便下载一个即可

② [Windows Login Unlocker](https://zhida.zhihu.com/search?content_id=240051295&content_type=Article&match_order=1&q=Windows+Login+Unlocker&zd_token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJ6aGlkYV9zZXJ2ZXIiLCJleHAiOjE3Nzk3NzkwODUsInEiOiJXaW5kb3dzIExvZ2luIFVubG9ja2VyIiwiemhpZGFfc291cmNlIjoiZW50aXR5IiwiY29udGVudF9pZCI6MjQwMDUxMjk1LCJjb250ZW50X3R5cGUiOiJBcnRpY2xlIiwibWF0Y2hfb3JkZXIiOjEsInpkX3Rva2VuIjpudWxsfQ.g6RC7OMqP_8zNEIJqR2xQ2fPifg38sBjLDBZSsK_Hu0&zhida_source=entity) 工具，文末提供下载方式！

![](./assets/绕过Windows微软账户登录和密码清除/一.jpg)

二、操作步骤

① 在另一台电脑将 WinPE 写入 U 盘，设置电脑从 U 盘启动，从而进入 PE 系统。这是常规操作，不会的可以百度一下，网上很多教程！

② 来到 WinPE 下，运行软件 Windows Login Unlocker。目前大部分的 WinPE 都没有集成这个软件，我们可以自行放到 U 盘里。它是一个绿色小程序，只有 300 多 KB，无需安装，双击即可运行。

![](./assets/绕过Windows微软账户登录和密码清除/二.jpg)

1.绕过开机密码
------

运行软件后，首先选择一个 Windows 系统，我这里只有一个系统。

![](./assets/绕过Windows微软账户登录和密码清除/1.1.jpg)

鼠标右键 → 绕过密码模式 → 确定。操作就完成了！

![](./assets/绕过Windows微软账户登录和密码清除/1.2.jpg)

![](./assets/绕过Windows微软账户登录和密码清除/1.3.jpg)

重启电脑后，登录界面多了一个管理员账号（本地账号），直接点“登录”，后面需要等一小会儿很快就进入桌面了。

![](./assets/绕过Windows微软账户登录和密码清除/1.4.jpg)

![](./assets/绕过Windows微软账户登录和密码清除/1.5.jpg)

很多人会想多了个本地账户怎么办？没有关系，下次重启后，此本地账户就自动消失了。神不知鬼不觉~

![](./assets/绕过Windows微软账户登录和密码清除/1.6.jpg)

2.清除开机密码
------

运行软件后，首先点击系统，选择一个账户（没有 ↓ 表示是当前启用的账户），再点击右下角【重置/解锁】，会提示该账户与微软账户关联，点击【确定】。

![](./assets/绕过Windows微软账户登录和密码清除/2.1.jpg)

稍等十几秒，提示“密码重置成功”！

![](./assets/绕过Windows微软账户登录和密码清除/2.2.jpg)

重启电脑后，来到登录界面，可以看到，密码输入框没有了，直接就进来了。

![](./assets/绕过Windows微软账户登录和密码清除/2.3.jpg)

3.总结
--

目前 Windows Login Unlocker 这款软件在 WinPE 中的普及度较低，一般 PE 默认的密码修改工具是直接修改 [SAM 文件](https://zhida.zhihu.com/search?content_id=240051295&content_type=Article&match_order=1&q=SAM%E6%96%87%E4%BB%B6&zd_token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJ6aGlkYV9zZXJ2ZXIiLCJleHAiOjE3Nzk3NzkwODUsInEiOiJTQU3mlofku7YiLCJ6aGlkYV9zb3VyY2UiOiJlbnRpdHkiLCJjb250ZW50X2lkIjoyNDAwNTEyOTUsImNvbnRlbnRfdHlwZSI6IkFydGljbGUiLCJtYXRjaF9vcmRlciI6MSwiemRfdG9rZW4iOm51bGx9._RE5nzBHM0zU5OxM8FaY6tLTtaHdxl4fQqP-QBUvdfA&zhida_source=entity) 进行重置密码，也就是下图这个工具。

![](./assets/绕过Windows微软账户登录和密码清除/3.jpg)

可随着 Windows 10/11 逐步变得普遍，一般用户也许会绑定微软账户使用。在这样的前提下，修改 SAM 重置密码已经不可能了，因为这部分的密码可能不存放在 SAM 文件。而 Windows Login Unlocker 支持解绑微软账户，强制转变为本地账户使用，这也是我推荐使用这个工具的原因，感兴趣的小伙伴可以自行下载试试！

原文链接：[绕过 Windows 微软账户登录和密码清除-爱学习的阿松 (itzyz.cn)](https://link.zhihu.com/?target=https%3A//www.itzyz.cn/archives/3099)

