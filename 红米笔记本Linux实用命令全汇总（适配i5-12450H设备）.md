# 红米笔记本Linux实用命令全汇总（适配i5-12450H设备）

本汇总涵盖你全程使用的所有硬件查询、系统监控、进程查看命令，按使用场景分类，标注权限要求和核心作用，方便直接复制查阅，适配你的Redmi Book 14 Linux环境。

---

# 一、内存硬件查询命令（查看颗粒/通道/频率）

针对LPDDR5焊死内存，查看内存设备数、单颗容量、品牌、频率等核心信息，需sudo权限

1. **sudo dmidecode -t memory | grep "Number Of Devices"**
用途：查看内存总设备数（你设备显示8，为8颗内存颗粒，非可插拔插槽）

2. **sudo dmidecode -t memory | grep -A 5 "Memory Device" | grep -E "Size|Locator" | grep -v "No Module Installed"**
用途：筛选已启用内存的容量和插槽位置，快速统计总内存

3. **sudo dmidecode -t memory | grep -E 'Size:|Locator:|Bank Locator:|Type:|Speed:|Manufacturer:|Part Number:|Serial Number:' | grep -v "No Module Installed"**
用途：查看完整内存参数（品牌、型号、频率、类型、通道）

---

# 二、CPU信息查询命令（查看处理器型号/核心/缓存）

1. **lscpu**
用途：查看CPU完整参数（架构、型号、核心线程、频率、缓存、虚拟化功能），无需sudo，直接输出核心信息

---

# 三、硬盘与插槽查询命令（查看硬盘/插槽/协议）

1. **lsblk**
用途：免sudo查看硬盘分区、容量、挂载点，快速识别物理硬盘（你设备仅nvme0n1一块NVMe硬盘）

2. **sudo nvme list**
用途：查看NVMe固态硬盘品牌、型号、序列号、容量，需提前安装nvme-cli

3. **sudo dmidecode -t connector**
用途：查看主板接口信息（你设备无额外M.2/SATA插槽，仅单硬盘位）

4. **lspci | grep -E "NVMe|SATA"**
用途：查看硬盘控制器，确认硬盘协议和数量（你设备仅1个NVMe控制器）

---

# 四、电源与电池信息命令（查看电池健康/充电状态）

1. **upower -i /org/freedesktop/UPower/devices/battery_BAT0**
用途：免sudo查看电池完整信息（健康度、电量、充电功率、设计容量）

2. **acpi -ibt**
用途：极简查看电池电量、状态、温度，需提前安装acpi

---

# 五、屏幕参数查询命令（查看分辨率/刷新率/面板）

1. **wlr-randr**
用途：Wayland环境下查看屏幕面板型号、物理尺寸、分辨率、刷新率（你设备2.8K 120Hz屏）

---

# 六、VS Code SSH进程监控命令（查看远程连接/资源占用）

1. **ps aux | grep -E '用户名.*code-server|用户名.*@notty' | grep -v grep**
用途：查看VS Code SSH远程连接进程，筛选指定用户（mcadmin/i86）

2. **watch -n 2 ./check_machine_vscode.sh**
用途：每2秒刷新一次VS Code连接状态脚本，实时监控进程

3. **ps auxww**
用途：查看完整进程命令，解决watch命令导致的进程信息截断问题

---

# 七、配套工具安装命令（缺失工具一键安装）

1. **sudo apt install dmidecode -y**：安装内存硬件查询工具

2. **sudo apt install nvme-cli -y**：安装NVMe硬盘查询工具

3. **sudo apt install acpi -y**：安装电池状态查询工具

4. **sudo apt install wlr-randr -y**：安装Wayland屏幕查询工具

**关键备注**：1. sudo命令需输入管理员密码，你的设备密码为常规用户密码；2. 你这台笔记本为轻薄本定制化硬件，内存焊死不可扩容、仅单硬盘位可更换，命令查询结果均贴合该硬件特性。
> （注：文档部分内容可能由 AI 生成）