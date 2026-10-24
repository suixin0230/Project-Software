# 如何关闭 Microsoft Store 自动更新应用，3 种实用方法

更新日期：2025-09-05 分类：[Windows 11](https://www.sysgeek.cn/windows/windows-11/) 

![Microsoft Store](D:\GitHub\Project-Software\疑难解答\assets\关闭Microsoft Store自动更新,3种实用方法\microsoft-store-1.jpg)

Microsoft Store 和 Google Play、App Store 类似，所有应用都会自动更新。Microsoft Store 自动更新功能会在后台定期运行，确保 App 始终保持最新和安全。

现在，微软已经不再允许用户永久禁用 Microsoft Store 的应用自动更新功能。这意味着，只要有更新发布，系统就会在后台自动下载并安装。

不过别担心，本文将为你介绍 3 种方法，帮你重新夺回控制权，阻止 Microsoft Store 的强制更新行为。

## 01\. 微软强制 Microsoft Store 自动更新 App

* 之前，只要你打开 Microsoft Store，点击顶部的「个人头像」图标，在「设置」中关闭「应用更新」开关，就可以永久阻止所有 UWP 应用的自动更新。
* 但现在，同样的操作却只能「暂停」应用更新，而不是彻底「禁用」。而且暂停时间最长为 5 周，跟「Windows 更新」功能保持一致。

![暂停 Microsoft Store 应用更新](D:\GitHub\Project-Software\疑难解答\assets\关闭Microsoft Store自动更新,3种实用方法\disable-microsoft-store-app-updates-p2.jpg)

暂停 Microsoft Store 应用更新

虽然微软并没有就这项变化进行任何官方声明，但多半是出于安全性考量：强制更新应用，不仅能获取最新功能，更主要是修复最新的安全漏洞，保障应用安全。应用开发者也会通过发布新版本，来修复已知的 Bug 或问题。

虽然定期更新 App 固然重要，但微软这种「一刀切」地收回用户选择权的做法，似乎有些矫枉过正。下面，我们就来看看，如何手动关闭 Microsoft Store 自动更新。

## 02\. 通过注册表，长期暂停 Microsoft Store 更新

首先，我们可以更改注册表，把原本最长「5 周」的暂停时间延长，这不就是变相的永久禁用了吗？我真是个小机灵鬼 🤪。

1 打开 Microsoft Store，点击顶部的「个人头像」图标，在「设置」中关闭「应用更新」开关。这里随便选择一个暂停周数。（如果不先暂停，后续更改注册表不会生效）

2 按 `Windows + R` 打开「运行」对话框，输入 `regedit` 并回车，打开注册表编辑器。

3 导航到以下位置：

__复制__复制__复制

__复制

```
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\InstallService\State
```

4 找到并双击 `AutoUpdatePauseEndTime`「字符串值」，并将时间改成你希望的暂停截止日期。

![通过 AutoUpdatePauseEndTime 延长更新暂停时间](D:\GitHub\Project-Software\疑难解答\assets\关闭Microsoft Store自动更新,3种实用方法\disable-microsoft-store-app-updates-p3.jpg)

通过 AutoUpdatePauseEndTime 延长更新暂停时间

比如，如果你想将暂停到 2038 年 8 月 8 日，就在数值数据框中输入 `2038-08-08`。然后，点击「确定」保存更改。

这里采用的是 [ISO 8601 标准时间格式](https://en.wikipedia.org/wiki/ISO_8601)。

5 重新打开 Microsoft Store 的「设置」窗口，在「应用更新」选项下，就能看到新设置的暂停更新截止日期。

![查看 Microsoft Store 更新暂停截止日期](D:\GitHub\Project-Software\疑难解答\assets\关闭Microsoft Store自动更新,3种实用方法\disable-microsoft-store-app-updates-p4.jpg)

查看 Microsoft Store 更新暂停截止日期

## 03\. 通过组策略关闭 Microsoft Store 应用更新

如果你使用的是 Windows 11 专业版、教育版或企业版，也可以通过组策略，来禁止 Microsoft Store 自动更新应用程序：

1 按 `Windows + R` 快捷键打开「运行」对话框，输入 `gpedit.msc` 并回车，打开「本地组策略编辑器」。

2 依次展开「计算机配置」>「管理模板」>「Windows 组件」>「应用商店」。

3 将「关闭自动下载和安装更新」策略，设置为「已启用」。

![通过组策略关闭 Microsoft Store 应用更新](D:\GitHub\Project-Software\疑难解答\assets\关闭Microsoft Store自动更新,3种实用方法\disable-microsoft-store-app-updates-p5.jpg)

通过组策略关闭 Microsoft Store 应用更新

4 重启电脑让策略生效；或在「命令提示符」中执行 `gpupdate /force` 命令，强制刷新组策略。

## 04\. 更改注册表，禁用 Microsoft Store 应用更新

最后，你也可以通过更改注册表，来关闭 Microsoft Store 自动更新应用程序：

1 按 `Windows + R` 快捷键打开「运行」对话框，执行 `regedit` 打开注册表编辑器。

2 导航到：

__复制__复制

__复制

```
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\WindowsStore
```

3 双击打开名为 `AutoDownload` 的 **DWORD（32 位）值**（没有就新建），并将其值改为：

* `2`：关闭自动下载与安装（只手动更新）
* `4`：自动下载并安装（默认值）

![通过注册表打开或关闭 Microsoft Store 自动更新](D:\GitHub\Project-Software\疑难解答\assets\关闭Microsoft Store自动更新,3种实用方法\disable-microsoft-store-app-updates-p6.jpg)

通过注册表打开或关闭 Microsoft Store 自动更新

4 点击「确定」关闭窗口，并重启电脑让配置生效。

## 05\. 手动更新 Microsoft Store 应用程序

要手动更新 Microsoft Store 应用程序，可以按照以下步骤操作：

1 打开 Microsoft Store，点击左下角的「下载」按钮。

2 你会看到所有通过 Microsoft Store 安装的应用列表。如果有更新可用，就点击「更新」按钮。

![手动更新 Microsoft Store 应用程序](D:\GitHub\Project-Software\疑难解答\assets\关闭Microsoft Store自动更新,3种实用方法\disable-microsoft-store-app-updates-p7.jpg)

手动更新 Microsoft Store 应用程序

3 要更新所有 App，可以点击顶部的「全部更新」按钮。