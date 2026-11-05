# “U 盘装完微 PE 后无法格式化”及“如何指定盘符”

请以 **管理员身份** 打开命令提示符，依次输入以下命令（每行按一次回车）：

### 一、清理与重建

1. `diskpart` （进入工具）
2. `list disk` （列出所有磁盘，**认准 U 盘大小和编号**）
3. `select disk X` （X 换成你的 U 盘编号，如 `select disk 2`）
4. `attributes disk clear readonly` （清除微 PE 可能写入的只读属性）
5. `clean` （⚠️ 彻底清空 U 盘，所有数据丢失）
6. `create partition primary` （创建新的主分区）

### 二、选中并格式化

7. `list partition` （列出刚建好的分区）
8. `select partition 1` （**关键：必须选中分区 1，否则格式化会报“没有选择卷”**）
9. `format fs=ntfs quick` （快速格式化为 NTFS，也可换成 `fat32` 或 `exfat`）

### 三、分配指定的盘符

10. `assign letter=G` （**将 G 替换为你想要的盘符**，确保该字母没被占用）
11. `exit` （退出 Diskpart）

---

### 💡 避坑

*   **不要直接输数字**：在 DiskPart 里，直接输入 `1` 会调出帮助菜单，必须输入具体的指令（如 `select partition 1`）。
*   **选对磁盘**：在执行 `clean` 之前，**务必用 `list disk` 反复确认 U 盘编号**，选错会把电脑硬盘全清空。
*   **盘符冲突**：如果提示盘符被占用，换个字母（如 H、I）即可。如果 `assign` 失败，也可以去系统的“磁盘管理”里右键 U 盘手动分配。
*   **物理开关**：如果做完上述步骤还是无法格式化，检查一下 U 盘侧面有没有“写保护”物理开关，有的话拨到解锁位置。