# 全场景Linux运维指令手册
> 中文版
> 该手册使用豆包生成
> 由于平时遇到不会的命令一条条查实在是太麻烦
> 故萌生了整理手册的想法
> 由于内容实在是太多，一晚上肝不完
> 内容几乎也还没有被审查
> 就等下次有时间的时候继续肝好了

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Stars](https://img.shields.io/github/stars/你的用户名/ubuntu2404-linux-commands.svg)
![Forks](https://img.shields.io/github/forks/你的用户名/ubuntu2404-linux-commands.svg)

## 🌟 手册简介
针对 Linux 系统打造的「全场景运维指令手册」，覆盖**基础操作、进阶运维、安全管理**三大维度，按使用频率排序，包含：
- ✅ 高频常用指令 + 冷门实用指令
- ✅ 风险等级标注（高危指令单独预警）
- ✅ 版本适配、依赖条件说明
- ✅ 可直接复制的实操示例
- ✅ 新手友好的简化指南与速查表

适用人群：Linux运维工程师、开发者、学生（用于学习/日常运维）

## 📚 目录导航
| 章节 | 内容 | 核心指令 |
|------|------|----------|
| [01-系统基础操作](01-系统基础操作.md) | 启动/重启、系统信息查看 | reboot、uname、timedatectl |
| [02-文件目录管理](02-文件目录管理.md) | 目录切换、创建/删除/复制 | cd、ls、mkdir、rm、rsync |
| [03-用户与权限管理](03-用户与权限管理.md) | 用户/组管理、ACL权限 | useradd、chmod、chown、setfacl |
| [04-进程管理](04-进程管理.md) | 进程查看、信号控制、优先级调整 | ps、top、kill、nice |
| [05-系统监控与性能分析](05-系统监控与性能分析.md) | CPU/内存/磁盘监控、瓶颈排查 | free、df、iostat、sar |
| [06-网络管理](06-网络管理.md) | 网络配置、端口查看、防火墙 | ip、ss、ufw、iptables |
| [07-软件包管理](07-软件包管理.md) | APT安装、源码编译 | apt、./configure、make |
| [08-磁盘管理与分区](08-磁盘管理与分区.md) | 磁盘查看、分区、挂载 | lsblk、fdisk、mount、fstab |
| [09-日志管理](09-日志管理.md) | 日志查看、过滤、轮转 | tail、grep、journalctl、logrotate |
| [10-压缩解压](10-压缩解压.md) | tar/zip/gzip/rar/7z格式 | tar、zip、unzip、gzip |
| [11-文本处理](11-文本处理.md) | 编辑、正则匹配、统计 | vim、sed、awk、wc |
| [12-远程管理](12-远程管理.md) | SSH登录、文件传输、FTP | ssh、scp、sftp、vsftpd |
| [13-环境变量配置](13-环境变量配置.md) | 临时/用户级/全局变量 | export、.bashrc、/etc/profile |
| [14-冷门实用指令](14-冷门实用指令.md) | screen、nohup、strace等 | screen、nohup、watch、strace |
| [15-内核管理](15-内核管理.md) | 内核参数、模块加载 | sysctl、modprobe、lsmod |
| [16-定时任务](16-定时任务.md) | crontab、anacron | crontab、anacron |
| [17-备份恢复](17-备份恢复.md) | 文件备份、系统镜像 | rsync、tar、dd、fsarchiver |
| [18-SELinux与AppArmor](18-SELinux与AppArmor.md) | 安全策略管理 | aa-status、getenforce、setenforce |
| [附录1-高危指令汇总](附录1-高危指令汇总.md) | 高危指令+规避方案 | rm、dd、iptables |
| [附录2-依赖工具安装](附录2-依赖工具安装.md) | 所有工具包安装命令 | tree、htop、sysstat等 |
| [新手快速入门](新手快速入门.md) | 简化版核心指令（入门必看） | - |
| [高频指令速查表](高频指令速查表.md) | 按场景分类（快速查阅） | - |

## 🚀 使用说明
1. **查阅方式**：
   - 新手：先看「新手快速入门.md」，掌握核心操作；
   - 日常运维：直接查「高频指令速查表.md」或对应章节；
   - 特殊需求：查看「冷门实用指令.md」或附录。

2. **指令使用注意**：
   - 标注「高危」的指令（如rm -rf、dd），务必先看「附录1-高危指令汇总.md」的规避方案；
   - 需依赖工具的指令（如tree、htop），先通过「附录2-依赖工具安装.md」安装对应包；
   - 示例中的路径（如/home/ubuntu）、用户名（如testuser）需根据实际环境修改。

3. **脚本使用**：
   - examples/目录下的脚本可直接下载执行，执行前需赋予权限：`chmod +x 脚本名.sh`；
   - 脚本内有详细注释，可根据需求修改参数。

## 🤝 贡献指南
欢迎大家参与完善手册！贡献流程：
1. Fork本仓库；
2. 创建分支：`git checkout -b feature/新增指令` 或 `fix/修正错误`；
3. 提交修改：
   - 新增指令需标注「版本适配、依赖条件、实操示例」；
   - 修正错误需验证指令有效性（基于Ubuntu 24.04 LTS）；
4. 提交PR（Pull Request），描述修改内容。

贡献规范：
- 指令格式统一（参考现有章节的「指令名+参数+示例」结构）；
- 新增脚本需确保可执行性。

## 📄 许可证
本仓库采用 [MIT License](LICENSE) 开源，允许自由使用、修改、分发，保留原作者版权声明即可。

## 📞 反馈与交流
- 发现错误/缺失指令：提交Issue（请注明「章节+指令名+问题描述」）；
- 交流运维经验：参与GitHub Discussions；
- 其他建议：直接联系仓库作者（mmili985@163.com）。
