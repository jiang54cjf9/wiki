# 🐧 Linux 基本命令速查表

> 适用于初学者和日常服务器管理，覆盖常用操作。

---

## 📂 文件与目录操作

| 命令 | 说明 | 示例 |
|------|------|------|
| `ls` | 查看当前目录下的文件 | `ls -l` 显示详细信息 |
| `cd` | 切换目录 | `cd /home` 进入 `/home` 目录 |
| `pwd` | 显示当前路径 | `pwd` |
| `mkdir` | 创建目录 | `mkdir newdir` |
| `rmdir` | 删除空目录 | `rmdir olddir` |
| `rm` | 删除文件或目录 | `rm file` 或 `rm -rf dir` |
| `cp` | 复制文件或目录 | `cp a.txt b.txt` |
| `mv` | 移动或重命名文件 | `mv old.txt new.txt` |
| `touch` | 创建空文件或修改时间戳 | `touch file.txt` |
| `cat` | 查看文件内容 | `cat /etc/hosts` |
| `more` / `less` | 分页查看文件 | `less file.txt` |
| `head` | 查看文件前几行 | `head -n 10 file.txt` |
| `tail` | 查看文件后几行 | `tail -f log.txt` 实时查看日志 |
| `vi` / `vim` | 文本编辑器 | `vi log.txt` 开始编辑log.txt |

---

## 🔍 文件搜索

| 命令 | 说明 | 示例 |
|------|------|------|
| `find` | 按条件查找文件 | `find / -name "*.conf"` |
| `locate` | 快速查找文件（需安装 `mlocate`） | `locate nginx.conf` |
| `grep` | 在文件中搜索内容 | `grep "error" log.txt` |
| `which` | 查找命令路径 | `which python3` |
| `whereis` | 查找命令及帮助文件位置 | `whereis nginx` |

---

## 🧍 用户与权限管理

| 命令 | 说明 | 示例 |
|------|------|------|
| `whoami` | 显示当前用户 | `whoami` |
| `su` | 切换用户 | `su root` |
| `sudo` | 以管理员权限执行命令 | `sudo reboot` |
| `passwd` | 修改用户密码 | `passwd` |
| `adduser` | 添加新用户 | `adduser user1` |
| `userdel` | 删除用户 | `userdel -r user1` |
| `chmod` | 修改权限 | `chmod 755 file.sh` |
| `chown` | 修改文件属主 | `chown root:root file` |

---

## 🧰 系统管理

| 命令 | 说明 | 示例 |
|------|------|------|
| `uname -a` | 查看系统信息 | `uname -a` |
| `hostname` | 查看或修改主机名 | `hostnamectl set-hostname myserver` |
| `top` | 动态查看系统进程与资源占用 | `top` |
| `htop` | 更友好的系统监控工具（需安装） | `htop` |
| `df -h` | 查看磁盘空间使用情况 | `df -h` |
| `du -sh` | 查看目录大小 | `du -sh /var/log` |
| `free -h` | 查看内存使用情况 | `free -h` |
| `uptime` | 查看系统运行时间与负载 | `uptime` |
| `reboot` | 重启系统 | `sudo reboot` |
| `shutdown -h now` | 立即关机 | `sudo shutdown -h now` |

---

## 🔥 进程管理

| 命令 | 说明 | 示例 |
|------|------|------|
| `ps -ef` | 查看所有进程 | `ps -ef | grep nginx` |
| `kill` | 终止进程 | `kill 1234` |
| `kill -9` | 强制终止进程 | `kill -9 1234` |
| `pgrep` | 按名称查找进程号 | `pgrep nginx` |
| `pkill` | 按名称结束进程 | `pkill nginx` |
| `systemctl` | 管理系统服务 | `systemctl restart nginx` |
| `service` | 管理服务（旧系统） | `service sshd status` |

---

## 🌐 网络管理

| 命令 | 说明 | 示例 |
|------|------|------|
| `ip addr` / `ifconfig` | 查看网卡信息 | `ip addr show` |
| `ping` | 测试网络连通性 | `ping 8.8.8.8` |
| `curl` | 访问网页或接口 | `curl http://example.com` |
| `wget` | 下载文件 | `wget http://example.com/file.zip` |
| `netstat` / `ss` | 查看网络端口与连接 | `ss -ltnp` |
| `firewall-cmd` | 管理防火墙 | `firewall-cmd --list-all` |
| `nmcli` | 管理网络连接 | `nmcli dev show` |

---

## 📦 软件包管理（CentOS / RHEL 系）

| 命令 | 说明 | 示例 |
|------|------|------|
| `yum install` | 安装软件 | `yum install nginx` |
| `yum remove` | 卸载软件 | `yum remove nginx` |
| `yum update` | 更新软件包 | `yum update` |
| `yum list installed` | 查看已安装的软件 | `yum list installed` |
| `rpm -qa` | 列出所有 rpm 包 | `rpm -qa | grep nginx` |
| `rpm -ql` | 查看包内文件 | `rpm -ql nginx` |

---

## 🧾 压缩与解压

| 命令 | 说明 | 示例 |
|------|------|------|
| `tar -czvf` | 打包并压缩为 `.tar.gz` | `tar -czvf backup.tar.gz /home` |
| `tar -xzvf` | 解压 `.tar.gz` 文件 | `tar -xzvf backup.tar.gz` |
| `zip -r` | 压缩为 zip 文件 | `zip -r backup.zip /home` |
| `unzip` | 解压 zip 文件 | `unzip backup.zip` |

---

## ⚙️ 权限数字速记表

| 权限 | 数值 | 说明 |
|------|------|------|
| 读 (r) | 4 | 允许读取 |
| 写 (w) | 2 | 允许写入 |
| 执行 (x) | 1 | 允许执行 |

> 示例：`chmod 755 file` → 所有者可读写执行，组用户和其他用户可读执行。

---

## 🧠 小技巧

- `Tab` 自动补全路径或命令  
- `Ctrl + C` 终止当前命令  
- `Ctrl + L` 清屏  
- `history` 查看历史命令  
- `!n` 重复执行第 n 条历史命令  
- `!!` 重复执行上一条命令  

---

📘 **推荐继续学习**
- `man <命令>`：查看命令帮助，如 `man ls`
- [Linux 官方文档](https://www.kernel.org/doc/)
- 学习路线建议：文件操作 → 权限管理 → 进程/网络 → 系统服务
