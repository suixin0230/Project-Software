# Windows 指定某单一程序启动时不弹出 UAC 通知的方法

**情形一：** 让软件 ==[以普通用户身份运行]== 并取消 UAC 提示

1.按 **Win+R 键** 打开 **[运行]** 窗口，输入 **regedit** 并点击 [确定] 按钮（或直接回车）

2.在 [注册表编辑器](https://zhida.zhihu.com/search?content_id=106927476&content_type=Article&match_order=1&q=注册表编辑器&zd_token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJ6aGlkYV9zZXJ2ZXIiLCJleHAiOjE3ODAyMTgxODAsInEiOiLms6jlhozooajnvJbovpHlmagiLCJ6aGlkYV9zb3VyY2UiOiJlbnRpdHkiLCJjb250ZW50X2lkIjoxMDY5Mjc0NzYsImNvbnRlbnRfdHlwZSI6IkFydGljbGUiLCJtYXRjaF9vcmRlciI6MSwiemRfdG9rZW4iOm51bGx9.uhHtA9619A1ElIb4Te-5Y-22vMSvr074h6dT36qiBS8&zhida_source=entity) 地址栏中输入

![注册表编辑器地址栏位置](./assets/Windows 指定某单一程序启动时不弹出 UAC 通知的方法/注册表编辑器地址栏位置.png)

`计算机\HKEY_CURRENT_USER\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`

​	若无 **Layers 文件夹**，可自己新建步骤：`右键 AppCompatFlags文件夹→新建(N)→项(K)→命名为：Layers`

3.进入 **Layers** 文件夹后，(注册表编辑器_右侧空白处)新建一个 [==字符串值(S)==]

​	字符串名称：指定软件的完整路径

​	右键 `新建的字符串` → 修改 → 数值数据：`RUNASINVOKER`

> [!CAUTION]
>
> **注意：** 若你打算添加新字符串值时，发现该 **注册表已存在**，那么说明你设置过该软件的 **兼容性**（右键 - 属性 - 兼容性 选项卡），遇到这种情况，你只需追加到最后就行了。
> 如：已存在注册表 **数值数据为：** `C:\Users\SVG\Desktop\YOUDAO~1\`
>
> 那么就改成：`C:\Users\SVG\Desktop\YOUDAO~1\ RUNASINVOKER`

**情形二：** 让软件 ==[以管理员身份运行]== 并不提示 UAC

1.开始菜单右键 - 计算机管理 *或者* 开始菜单 - 搜索 - 计算机管理 打开即可；

2.系统工具 - 任务计划程序 - 任务计划程序库，点击右侧 **操作** - **[任务计划程序库]** 下面

`创建任务`

3.进入 `创建任务` 窗口

​	常规 - 名称(随意，自己能辨认出即可) - ☑ 使用最高权限运行(==记得勾选==)

​	操作 - 新建 - 【新建操作 - 程序或脚本 - 浏览】 - 选择程序路径后 - 确定

4.新建快捷方式来方便我们之后运行

​	桌面 - 右键(空白处) - 新建 - 快捷方式 - 【快捷方式的位置填写为：`schtasks.exe /run /tn "计划任务名称"`】 - 下一步 - 名称(随意自，己能辨认出即可) - 完成

> ​	其实，无需将快捷方式放入 Startup 文件夹。利用计划任务自带触发器，添加触发器设置为“启动时”或者“登录时”亦可实现自启动

**情形二也可以用工具来实现**

​	工具名称：`UAC Whitelist Tool`

​	下载地址：[UAC Whitelist Tool(UAC 白名单小工具)](https://github.com/XIU2/UACWhitelistTool)

## 使用说明（具体使用方法见作者主页）

作者：XIU2

1. **[拖拽]** 或 **[浏览]** 选择一个应用程序 (.exe) 或脚本 (.bat) 或快捷方式 (.lnk) 。
2. [程序名称] 随意，但必须唯一 不可重复。
3. [启动参数] 与 [起始位置] 均可选。
4. **[添加至 UAC 白名单]** 后，[桌面] 就会出现一个快捷方式，只有通过该快捷方式运行才不提示 UAC！(运行后默认拥有管理员权限)

> **注意：** 生成于桌面的快捷方式可以复制、移动、重命名，不影响使用！
> **注意：** 为了方便寻找和删除，添加白名单时 [程序名称] 前会添加 [noUAC.] 标识。
> **另外，** 因添加任务计划需要管理员权限，所以本软件运行会提示 UAC，但可以把本软件添加到 UAC 白名单中！

## 其他说明：

**运行提示 .NET 错误？**

本软件最低依赖是 .NET Framework 4.5，报错说明你系统的该依赖版本低于 4.5（Win10 默认满足该依赖），请安装更高版本的 [.NET Framework](https://link.zhihu.com/?target=https%3A//dotnet.microsoft.com/download/dotnet-framework) ！
