---
title: 基础命令之cp命令
date: 2017-02-17 18:05:09
tags: [man]
---

## 描述
`cp`：copy files and directories，拷贝文件或目录到指定位置;

## 格式
```bash
$ cp [选项] [SRC] [DEST]
```

<!-- more -->

## 选项
+ `-a`：归档存放；
+ `-r/-R`：递归复制目录；
+ `-f`：强行复制文件或目录，不论目标文件或目录是否存在；
+ `-p`：保留文件属性(时间戳)并复制；
+ `-i`：若目标文件已存在，覆盖已存在的目标文件之前询问用户是否覆盖；
+ `-b`：若目标文件已存在，覆盖已存在的目标文件前先将目标文件备份；
+ `-S`：在备份文件时，使用指定后缀代替默认后缀`~`；
+ `-v`：获取执行过程；

## 命令示例
+ 复制指定文件到指定目录
```bash
$ cp FILE /tmp/
```
+ 复制指定目录到指定目录
```bash
$ cp -r DIR /tmp/
```
+ 强制复制指定文件到指定目录
```bash
$ cp -f FILE /tmp/
```
+ 备份文件并指定其后缀
```bash
$ cp -S ".bk" -b FILE /tmp/
```
+ 将指定文件复制到多个指定位置
```bash
# 语法格式
$ echo DIR... | xargs -n 1 -I {} cp SRC {}
# 命令示例
$ echo /tmp/ /mnt/ | xargs -n 1 -I {} cp anaconda-ks.cfg {}
```