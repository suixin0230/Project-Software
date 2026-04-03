###### 方法一：关闭按流量计费的连接并运行相应代码

1.1 按【Win+i键】打开设置
1.2 点击【网络和Internet】；点击【WLAN】
1.3 点击【属性】
1.4 【按流量计费的连接】设置为【关】
1.5 按【Win+X键】；点击【终端管理员】
1.6 输入【DISM /Online /Add-Capability /CapabilityName:App.WirelessDisplay.Connect~~~~0.0.1.0】；按【回车（Enter键）】
1.7 提示【操作成功完成】（方法一完成）

###### 方法二：启动Windows Installer和Windows update服务

2.1 按【Win+R键】打开运行窗
2.2 输入【services.msc】；点击【确定】打开服务
2.3 双击【Windows Installer】
2.4 点击【启动】；点击【确定】
2.5 双击【Windows更新（也叫Windows Update）】
2.6 点击【启动】；点击【确定】（方法二完成，添加成功后可修改回去）

###### 方法三：删除DataStore和Download文件夹

3.1 打开【C盘】；双击【Windows（文件夹）】
3.2 双击【SoftwareDistribution（文件夹）】
3.3 选中【DataStore（文件夹）】和【Download（文件夹）】右键【删除】（方法三完成）附加：如果提示占用无法删除，依次操作【Win+R键】-【输入 resmon】-【CPU（右上角）】-【搜索句柄 输入 DataStore 或 Download】-【右键 结束进程 结束进程】