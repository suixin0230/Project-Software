# 出现问题，你的PIN不可用。单击以重新设置PIN 解决办法？

1.Windows登陆界面shift不松手点击重启

2.疑难解答---高级选项--命令提示符---输入Regedit---回车

3.选中hkey-local-machine点击左上角文件---加载配置单元

4.选择此电脑---系统盘---windows---system32---config---software

5.打开software（此时需要自定义一个名称，随便输入一个名称）
	①双击hkey-local-machine---刚才自定义名称文件夹---microsoft---windowsnt
---currentversion---passwordless---device
	②双击device→选中右边devicepasswordlessbuildversion并双击
将数据2修改为0，确定
	③返回找到自定义名称文件夹然后选中---左上角文件---卸载配置单元---是

6.关闭---继续使用windows

7.登陆选项改为微软账户密码登录---进入系统后---重新设置PIN码即可

