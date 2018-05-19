# Information Science Basic

## 计算机基础
- 计算机的组成
- 操作系统
- 计算机是如何启动的
- Unix传奇
- Windows 与 Mac OSX的恩怨
- Linux的崛起

**实验：组装电脑并且安装LINUX系统**

## Bash
- Linux vs Windows
- Linux 特性
- Ubuntu 简介
- Ubuntu系统管理与数据操作

**实验：通过bash命令管理系统数据、用户**

## Editor
- 编辑器的概念以及选择
- VIM简介和学习方法
- VIM基本编辑方法
- VIM模式和移动查询

**实验：使用VIM编辑文本查询数据**

## Version
- 为何需要版本控制系统
- 如何安装版本控制
- 版本库和工作区
- 控制数据版本的流程
- 查询数据的历史信息

**实验：使用Git管理数据的版本状态**

## Table Data
- 数据表的基本概念
- 数据类型与操作
- 数据过滤与查询
- 如何高效处理数据

**实验：使用CSV文本编辑处理数据表**



EASYBCD

1. 修改配置
```
title Install Ubuntu
root (hd0,0)
kernel (hd0,0)/vmlinuz.efi boot=casper iso-scan/filename=/ubuntu-16.04.2-desktop-amd64.iso ro quiet splash locale=zh_CN.UTF-8
initrd (hd0,0)/initrd.lz
```
2.   `ubuntu-16.04.2-desktop-amd64.iso` `casper/initrd.lz` `casper/vmlinuz.efi` `.disk文件夹` 复制到C盘


sudo umount -l /isodevice
