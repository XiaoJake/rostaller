# 1 特性

用于在 Linux Ubuntu 环境中一键安装 ROS 1，通过 `rosdistro` 库的最新版本（使用 `wget` 获取）或本地内置版本自动处理 `rosdep init` 和 `rosdep update` 失败的问题（域名污染），无需繁琐设置。

- 支持版本：

  - Ubuntu 14.04（Trusty） + ROS 1 Indigo
  - Ubuntu 16.04（Xenial） + ROS 1 Kinetic
  - Ubuntu 18.04（Bionic） + ROS 1 Melodic
  - Ubuntu 20.04（Focal） + ROS 1 Noetic
  - ARM 架构内核，将SimpleSources文件夹中的source.list中，所有源中，ubuntu改为ubuntu-ports即可

- 执行过程同时输出至终端及 log 文件

- 若连接 Key 服务器失败，请多尝试几次

- 变更历史请参考 [CHANGELOG](CHANGELOG.md)

# 2 用法

## 2.1 克隆仓库

```bash
git clone https://github.com/RocShi/rostaller.git
```

## 2.2 进入仓库目录

```bash
cd rostaller
```

## 2.3 为脚本添加可执行权限

```bash
chmod +x ./run.sh
```

## 2.4 可选项-延长sudo记住密码打时长

```bash
#每次使用sudo命令时，输入密码，系统默认只会记住5分钟，5分钟内运行sudo相关命令都不会要求输入密码，5分钟后就需要人手动再次输入密码。
#我们装ros的过程肯定不止5分钟，防止脚本执行过程中卡在输入密码的某一步不动，建议延长这个时间到30分钟

sudo vim /etc/sudoers
#找到 Defaults env_reset 这一行
#将其改成 Defaults env_reset, timestamp_timeout=30
#强制保存退出 :wq!

```

## 2.5 运行脚本

```bash
./run.sh
```

**Enjoy ROS！**
