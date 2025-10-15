# Scoop 使用指南

[GitHub 链接](https://github.com/ScoopInstaller/Scoop)

## 介绍

windows 上的包管理器，使用时需要代理

```
$Env:HTTPS_PROXY="http://127.0.0.1:10809"
```

## 安装

打开终端（非管理员），按步骤输入以下代码进行安装

```
$Env:HTTPS_PROXY="http://127.0.0.1:10809"

Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression

scoop install aria2
```

## 常用指令

### 🧩 基础命令

| 命令 | 说明 |
|------|------|
| `scoop help` | 显示帮助信息 |
| `scoop --version` | 查看 Scoop 版本 |
| `scoop status` | 查看当前已安装软件的状态 |


### 📦 安装与卸载应用

| 命令 | 说明 |
|------|------|
| `scoop install <软件名>` | 安装应用 |
| `scoop uninstall <软件名>` | 卸载应用 |
| `scoop update <软件名>` | 更新指定应用 |
| `scoop update *` | 更新所有已安装的应用 |
| `scoop info <软件名>` | 查看软件信息 |
| `scoop search <关键字>` | 搜索可安装的软件 |
| `scoop list` | 列出已安装的软件 |
| `scoop checkup` | 检查 Scoop 环境问题并提供修复建议 |

### 🗂️ 仓库（Bucket）管理
> 有些包或者软件需要先加入仓库才能搜索与安装

| 命令 | 说明 |
|------|------|
| `scoop bucket list` | 查看当前添加的仓库列表 |
| `scoop bucket known` | 查看所有已知的官方/社区仓库 |
| `scoop bucket add <仓库名>` | 添加新的仓库（如 extras、versions、java） |
| `scoop bucket add <仓库名> <仓库URL>` | 从自定义地址添加仓库 |
| `scoop bucket rm <仓库名>` | 移除仓库 |

| 仓库名称 | 描述 |
|-----------|------|
| `main` | 默认仓库，包含常见的非图形界面（non-GUI）应用程序。 |
| `extras` | 额外仓库，存放不符合 main 仓库标准的应用程序。 |
| `games` | 开源和免费的视频游戏及相关工具。 |
| `nerd-fonts` | Nerd Fonts 字体集合。 |
| `nirsoft` | 收录来自 Nirsoft 的 250+ 实用工具集合。 |
| `sysinternals` | 微软发布的 Sysinternals 系列系统工具。 |
| `java` | 包含 Java 开发工具包（JDK）、运行时环境（JRE）、虚拟机调试工具及基于 Java 的运行引擎。 |
| `nonportable` | 非便携式应用程序（可能会触发 UAC 提示）。 |
| `php` | 各版本 PHP 的安装包。 |
| `versions` | 提供其他仓库中应用程序的备用或旧版本。 |


### 🔄 全局更新与清理

| 命令 | 说明 |
|------|------|
| `scoop update` | 更新 Scoop 自身及所有仓库 |
| `scoop cleanup` | 清理旧版本的包文件（释放磁盘空间） |
| `scoop cleanup <软件名>` | 清理指定应用的旧版本 |
| `scoop cache rm *` | 清除下载缓存 |

### 🔧 全局（系统级）安装

| 命令 | 说明 |
|------|------|
| `sudo scoop install <软件名>` | 以管理员权限全局安装软件 |
| `scoop prefix <软件名>` | 显示软件安装路径 |
| `scoop export > scoop-list.json` | 导出当前软件列表 |
| `scoop import scoop-list.json` | 从列表文件批量安装应用 |

### 示例
```
# 安装 Git
scoop install git

# 更新所有已安装软件
scoop update *

# 搜索 VSCode
scoop search vscode

# 添加 Java 仓库并安装 JDK
scoop bucket add java
scoop install openjdk

# 清理旧版本包
scoop cleanup *
```

## 建议
每次需要安装软件前或隔一段时间最好先更新一下scoop

```
$Env:HTTPS_PROXY="http://127.0.0.1:10809"

scoop update

scoop status

scoop update <软件名> / *

```

## 切换软件版本

```
scoop bucket add versions
scoop install nodejs@18.17.1
scoop install nodejs@20.11.0
scoop reset nodejs@18.17.1  # 切换到 Node 18
node -v                     # 验证
```

