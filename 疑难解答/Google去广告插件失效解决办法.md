# Google去广告插件失效解决办法

1. 新建txt文件，将下面内容粘贴进该文档中并更改文档后缀为（.txt→==.reg==），回车后双击文件即可导入txt

   
   Windows Registry Editor Version 5.00【HKEY_CURRENT_USER\Software\Policies\Google\Chrome】

   "ExtensionManifestV2Availability"=dword:00000002txt

   

2. 在 HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Google\Chrome 下新建一个注册表值 ExtensionManifestV2Availability，类型为 DWORD（32 位）值，修改数据为2

3. 重启Google Chrome浏览器即可