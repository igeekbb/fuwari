---
title: Debian 我的常用一键脚本
published: 2024-09-21
description: ''
image: ''
tags: []
category: ''
draft: false 
lang: ''
---
记录一下我最常用的 VPS 一键脚本
可能有安全隐患,仅供我个人使用.
#### 萌咖大佬一键DD脚本

```bash 更新
apt-get update
```

```bash 安装必备工具
apt-get install -y xz-utils openssl gawk file
```
```bash 全自动一键安装 debian 12
bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -d 12 -v 64 -p 登录密码 -a
```
更多参考:https://github.com/Tasle/InstallNET

#### 一键更新系统
```bash
apt update -y && apt full-upgrade -y && apt autoremove -y && apt autoclean -y
```

```bash 查看 Debian 版本
cat /etc/debian_version
```

#### 一键安装 wget curl git
```bash
apt install sudo curl wget 
```
#### 一键替换最新内核 BBR (卸载内核版本)

```bash
wget -O tcp.sh "https://github.com/ylx2016/Linux-NetSpeed/raw/master/tcp.sh" && chmod +x tcp.sh && ./tcp.sh
```
我一般选择 BBRplus 5 -> 19
弹出提示选择 NO

#### 一键 IP 质量体检和解锁检测

```bash
bash <(curl -Ls IP.Check.Place)
```