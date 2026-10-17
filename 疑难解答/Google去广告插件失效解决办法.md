# Google 去广告插件失效解决办法

### 方法一

1. 新建 txt 文件，将下面内容粘贴进该文档中并更改文档后缀为（.txt→ ==.reg==），回车后双击文件即可导入 txt

   
   Windows Registry Editor Version 5.00【HKEY_CURRENT_USER\Software\Policies\Google\Chrome】

   "ExtensionManifestV2Availability" = dword: 00000002txt

   

2. 在 HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Google\Chrome 下新建一个注册表值 ExtensionManifestV2Availability，类型为 DWORD（32 位）值，修改数据为 2

3. 重启 Google Chrome 浏览器即可

### 方法二

右键桌面 Google Chrome 快捷方式，【具体路径：Google Chrome 快捷方式 → 属性 → 目标】在浏览器快捷方式目标路径 *==后面==* 输入 `--disable-features=ExtensionManifestV2Unsupported,ExtensionManifestV2Disabled`

`--` 前面有一个空格