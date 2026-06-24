### ⚡ 常用命令速查（高频必备）

| 用途                 | 命令                                         |
| -------------------- | -------------------------------------------- |
| **查看设备**         | `adb devices`                                |
| **无线连接**         | `adb connect 192.168.1.100:5555`             |
| **安装应用**         | `adb install -r app.apk`（-r 覆盖保留数据）   |
| **卸载应用**         | `adb uninstall com.example.pkg`              |
| **推送文件**         | `adb push 本地文件 /sdcard/`                 |
| **拉取文件**         | `adb pull /sdcard/文件 ./`                   |
| **进入 Shell**        | `adb shell`                                  |
| **查看日志**         | `adb logcat -v time`（带时间戳）             |
| **过滤日志**         | `adb logcat \| grep 关键词`                  |
| **启动 Activity**     | `adb shell am start -n 包名/类名`            |
| **强制停止应用**     | `adb shell am force-stop 包名`               |
| **模拟点击**         | `adb shell input tap X Y`                    |
| **模拟滑动**         | `adb shell input swipe X1 Y1 X2 Y2`          |
| **模拟输入文字**     | `adb shell input text "内容"`                |
| **截屏**             | `adb shell screencap /sdcard/screen.png`     |
| **查看分辨率**       | `adb shell wm size`                          |
| **查看系统版本**     | `adb shell getprop ro.build.version.release` |
| **重启设备**         | `adb reboot`                                 |
| **重启到 Recovery**   | `adb reboot recovery`                        |
| **重启到 Bootloader** | `adb reboot bootloader`                      |
| **重启 ADB 服务**      | `adb kill-server` + `adb start-server`       |

---

### 📋 完整命令列表（分类详解）

#### 一、服务与设备管理
| 命令               | 说明                                   |
| ------------------ | -------------------------------------- |
| `adb start-server` | 启动 ADB 服务                            |
| `adb kill-server`  | 停止 ADB 服务                            |
| `adb devices`      | 列出所有已连接的设备                   |
| `adb devices -l`   | 列出设备并显示产品/型号信息            |
| `adb get-state`    | 获取设备状态（device/offline/unknown） |
| `adb get-serialno` | 获取设备序列号                         |
| `adb get-devpath`  | 获取设备路径                           |
| `adb version`      | 查看 ADB 版本                            |
| `adb help`         | 查看 ADB 帮助信息                        |

#### 二、设备连接（USB / 网络）
| 命令                         | 说明                    |
| ---------------------------- | ----------------------- |
| `adb connect <IP>:<端口>`    | 通过网络连接远程设备    |
| `adb disconnect <IP>:<端口>` | 断开远程设备连接        |
| `adb usb`                    | 将设备切换到 USB 连接模式 |

**多设备指定参数**：  
- `-d`：指定当前唯一的 USB 设备  
- `-e`：指定当前唯一的模拟器  
- `-s <序列号>`：指定特定设备（示例：`adb -s 设备号 shell wm size`）

#### 三、应用管理
| 命令                                       | 说明                     |
| ------------------------------------------ | ------------------------ |
| `adb install <APK路径>`                    | 安装应用                 |
| `adb install -r <APK路径>`                 | 覆盖安装（保留数据）     |
| `adb install -d <APK路径>`                 | 允许降级安装             |
| `adb uninstall <包名>`                     | 卸载应用                 |
| `adb uninstall -k <包名>`                  | 卸载应用但保留数据缓存   |
| `adb shell pm list packages`               | 列出所有已安装应用的包名 |
| `adb shell pm clear <包名>`                | 清除应用数据             |
| `adb shell pm grant <包名> <权限>`         | 授予应用权限             |
| `adb shell pm revoke <包名> <权限>`        | 撤销应用权限             |
| `adb shell pm reset-permissions -p <包名>` | 重置应用权限             |

#### 四、文件传输
| 命令                             | 说明                     |
| -------------------------------- | ------------------------ |
| `adb push <本地路径> <设备路径>` | 将文件从电脑推送到设备   |
| `adb pull <设备路径> <本地路径>` | 将文件从设备拉取到电脑   |
| `adb remount`                    | 重新挂载系统分区为可读写 |
| `adb root`                       | 以 root 权限重启 ADB        |

#### 五、设备重启与模式切换
| 命令                    | 说明                        |
| ----------------------- | --------------------------- |
| `adb reboot`            | 正常重启设备                |
| `adb reboot recovery`   | 重启进入 Recovery 模式        |
| `adb reboot bootloader` | 重启进入 Bootloader/刷机模式 |
| `adb reboot fastboot`   | 重启进入 Fastboot 模式        |

#### 六、日志与调试
| 命令                          | 说明                                               |
| ----------------------------- | -------------------------------------------------- |
| `adb logcat`                  | 查看设备日志                                       |
| `adb logcat -c`               | 清除日志缓存                                       |
| `adb logcat -d`               | 输出日志后退出                                     |
| `adb logcat -v time`          | 带时间戳显示日志                                   |
| `adb logcat \| grep <关键词>` | 过滤指定关键词的日志                               |
| `adb bugreport`               | 导出完整设备信息报告（含 dumpstate/dumpsys/logcat） |

#### 七、Shell 系统命令
| 命令                                         | 说明                  |
| -------------------------------------------- | --------------------- |
| `adb shell`                                  | 进入设备 Shell 交互模式 |
| `adb shell <命令>`                           | 直接执行单条 Shell 命令 |
| `adb shell getprop`                          | 获取所有系统属性      |
| `adb shell getprop ro.build.version.release` | 获取 Android 系统版本   |
| `adb shell getprop ro.product.manufacturer`  | 获取设备制造商        |
| `adb shell getprop ro.product.model`         | 获取设备型号          |
| `adb shell cat /proc/cpuinfo`                | 查看 CPU 信息           |
| `adb shell df`                               | 查看磁盘空间使用情况  |
| `adb shell dumpsys`                          | 获取各类系统状态信息  |
| `adb shell ps`                               | 查看所有运行中的进程  |
| `adb shell kill -9 <PID>`                    | 强制终止指定进程      |
| `adb shell netstat`                          | 查看网络状态          |
| `adb shell ifconfig`                         | 查看网络接口信息      |
| `adb shell pwd`                              | 查看当前工作目录      |
| `adb shell mkdir <路径>`                     | 创建目录              |
| `adb shell rm <路径>`                        | 删除文件              |
| `adb shell rmdir <路径>`                     | 删除目录              |
| `adb shell test -e <路径>`                   | 检查文件是否存在      |
| `adb shell ls -l <路径>`                     | 查看文件权限          |

#### 八、屏幕操作
| 命令                                | 说明                |
| ----------------------------------- | ------------------- |
| `adb shell screencap <路径>`        | 截屏并保存          |
| `adb shell screenrecord <路径>`     | 录屏                |
| `adb shell wm size`                 | 查看/修改屏幕分辨率 |
| `adb shell input text <文本>`       | 模拟文本输入        |
| `adb shell input keyevent <键码>`   | 模拟按键事件        |
| `adb shell am start -n <包名/类名>` | 启动 Activity        |
| `adb shell am force-stop <包名>`    | 强制停止应用        |

#### 九、模拟器专用
| 命令                                               | 说明                 |
| -------------------------------------------------- | -------------------- |
| `adb emu <命令>`                                   | 执行模拟器控制台命令 |
| `android list targets`                             | 显示所有 Android 平台  |
| `android list avd`                                 | 显示所有 AVD 模拟器    |
| `android create avd --name <名称> --target <编号>` | 创建 AVD              |
| `android delete avd --name <名称>`                 | 删除 AVD              |
| `emulator -avd <名称>`                             | 启动模拟器           |
| `mksdcard <容量> <路径>`                           | 创建 SD 卡镜像         |

---

> **注意**：部分命令（如 `adb remount`、`adb root`）需要 root 权限；不同 Android 版本对命令的支持可能存在差异。



# 应用包管理命令（最核心，与你最相关）

| 命令                                        | 功能说明                                       | **华为/荣耀系统建议**                                        |
| :------------------------------------------ | :--------------------------------------------- | :----------------------------------------------------------- |
| `adb shell pm list packages`                | 列出手机里 **所有** 应用的包名                   | 配合 `| findstr 视频` 或 `| grep huawei` 进行筛选查找。      |
| `adb shell pm disable-user --user 0 <包名>` | **【强烈推荐】** 将应用 **停用/隐藏** 给当前用户 | **解决你之前弹窗的终极方案**。应用状态会变成“已停用”，桌面消失，系统底层不再检测要求恢复，且随时可一键恢复，**绝对安全**。 |
| `adb shell pm enable <包名>`                | **恢复** 被停用（disable）的应用                | 如果某天想用了，用这个命令直接恢复，不需要重新安装。         |
| `adb shell pm uninstall -k --user 0 <包名>` | **【危险】** 彻底卸载预装应用                  | 卸载后仅恢复出厂设置才能找回来【建议提前备份安装包】。       |
| `adb shell pm install-existing <包名>`      | 恢复刚才被强制卸载（uninstall）的应用          | 如果不小心用 `uninstall` 卸载错了，用这个命令重新安装回系统。 |
| `adb shell pm clear <包名>`                 | 清除某个应用的全部数据（相当于重置）           | 如果某应用卡死或弹窗报错，清空数据可能直接解决问题。         |

## 日常实用及其他命令

*   **📸 截屏与录屏（免 ROOT）**
    *   `adb shell screencap /sdcard/屏幕截图.png` （截屏保存到手机内部存储）
    *   `adb shell screenrecord /sdcard/录屏.mp4` （录制手机屏幕，按 `Ctrl+C` 停止）
*   **📁 文件传输（免数据线传大文件）**
    *   `adb push 电脑上的文件路径 手机存储路径` （从电脑传到手机）
    *   `adb pull 手机里的文件路径 电脑存储路径` （从手机拉取到电脑）
*   **🖱️ 模拟操作（自动化神器）**
    *   `adb shell input tap X坐标 Y坐标` （模拟点击屏幕指定位置）
    *   `adb shell input swipe x1 y1 x2 y2 时长` （模拟滑动屏幕）
    *   `adb shell input text "你好"` （直接向当前输入框输入文字）
*   **📈 系统硬件监控**
    *   `adb shell dumpsys battery` （查看电池健康度、温度、电压等详细状态）
    *   `adb shell dumpsys meminfo` （查看内存占用情况）
    *   `adb shell dumpsys wifi` （查看 Wi-Fi 连接的底层日志）

### ⚠️ 终极警告（必看）

1. **不要把 `pm disable-user` 和 `pm uninstall` 混用。** 

   **对于系统应用、系统依赖项（如钱包 SDK），一定只能用 disable（停用）。**

2. 如果误删了系统极其核心的组件导致手机 **黑屏、无限重启**，不要慌张，**不需要刷机**。

   只要你能进入 `fastboot` 模式，重新连接电脑，执行 `adb shell pm install-existing <包名>` 或者直接 `adb reboot` 重启通常就能救回来。