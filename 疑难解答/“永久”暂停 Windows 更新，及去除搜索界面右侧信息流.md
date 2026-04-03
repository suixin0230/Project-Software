###### 1.“永久”暂停 Windows 更新

进入注册表，在下方路径：

"HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WindowsUpdate\UX\Settings"

右边→新建

名称：FlightSettingsMaxPauseDays	类型：DWORD(32 位)值(D)

基数：十进制				值：最大暂停天数(不要设置太大)；如：3000 及其以下 



###### 2.Windows10 去掉信息流：

若最后没有"explorer项"自己在左边*\Windows项下面新建一个

"HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Windows\explorer" 

再次在"explorer项"下面	右边→新建

名称：DisableSearchBoxSuggestions

类型：dword		基数：十六进制		值：1



> [!NOTE]
>
> *若要恢复更新暂停限制，可将 FlightSettingsMaxPauseDays 的值改回默认（或删除该键值）。*
> *若要恢复搜索建议，可将 DisableSearchBoxSuggestions 的值改为 0 或删除该键值。*