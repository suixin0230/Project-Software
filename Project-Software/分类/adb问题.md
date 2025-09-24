# ADB

1. 柚坛工具箱点击应用管理获取应用列表闪退解决办法

设置→系统→可选功能→相关设置→更多Windows功能→

启用以下功能

（.NET Framework 3.5(包括 .NET 2.0 和 3.0)
Windows Communication Foundation HTTP 激活
Windows Communication Foundation 非HTTP 激活
NET Framework 4.8 Advanced Services

ASP.NET 4.8）而后按照提示确定重启即可



2. 关于卸载应用，加入一个常见错误：DELETE_FAILED_INTERNAL_ERROR

对于卸载内置应用，使用常规的
pm uninstall package_name
会出现错误DELETE_FAILED_INTERNAL_ERROR，我之前就遇上了好几次，在网上说需要设置--user，正确代码为：
pm uninstall --user 0 package_name