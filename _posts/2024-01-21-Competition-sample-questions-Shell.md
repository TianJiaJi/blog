---
layout: post
title: Shell教程-中等院校职业技能大赛
author: TianJiaJi
date: 2024-01-21 12:00:00 +0800
categories: [博客,教程,职业技能大赛]
header-style: text
catalog:      true
tags:
    - 教程
    - 职业技能大赛
pin: true
math: true
mermaid: true
# render_with_liquid: true
---

***
# Shell脚本
***
## 题目

任务描述：请采用 shell 脚本,实现快速批量的操作。

1.  在 linux4 上编写/root/createfile.sh的shell脚本，创建20个文件/root/shell/file00至/root/shell/file19，如果文件存在，则删除再创建； 每个文件的内容同文件名， 如file00文件的内容为“file00”。
2. 用/root/createfile.sh命令测试。

## 教程

1.创建createfile.sh脚本文件
```shell
vim /root/createfile.sh
```

2.写入脚本代码
```shell
#!/bin/bash

# 创建目录
mkdir -p /root/shell

# 创建文件
for i in $(seq -f "%02g" 0 19)
do
    file="/root/shell/file$i"
    # 如果文件存在，则删除
    if [ -e $file ]; then
        rm $file
    fi
    # 创建文件并设置内容
    echo "file$i" > $file
done
```

3.运行脚本
```shell
sh /root/createfile.sh
```