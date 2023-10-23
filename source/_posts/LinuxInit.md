---
title: Linux 安装完时常用初始化指令
categories: Linux
tags:
    - Linux
    - 安装
    - 环境
---

# Shell

- 查看内存 `free -h`
- 查看磁盘 `df -h`


# Swap


~~~bash
sudo fallocate -l 2G /swapfile && sudo chmod 600 /swapfile && sudo mkswap /swapfile && sudo swapon /swapfile && echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
~~~


  - 1.创建 Swap 分区文件
   `dd if=/dev/zero of=/data2/swapfile bs=1M count=1024`
    - bs:    每块的大小
    - count: 块的数量
    - bs*count == swap文件大小
  - 2.格式化 Swap 分区文件
    `mkswap SwapFile`
      - 注:路径和之前的路径要对应
  - 3.启用 Swap 分区文件
    `swapon SwapFile
  - 4.添加开机启动
    把 `SwapFile swap swap defaults 0 0` 添加到 /etc/fstab

# Shell
  - dos2unix
    - dos2unix 是将 Windows 格式文件转换为 Unix、Linux 格式的实用命令.
    - Windows 格式文件的换行符为\r\n ,而 Unix&Linux 文件的换行符为\n.
    - dos2unix 命令可以将文件中的\r\n 转换为\n.

# Aria2

~~~bash
wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubiBackup/doubi/master/aria2.sh && chmod +x aria2.sh && bash aria2.sh

wget -N --no-check-certificate https://www.moerats.com/usr/shell/Aria2/aria2.sh && chmod +x aria2.sh && bash aria2.sh
~~~