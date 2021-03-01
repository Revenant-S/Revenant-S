---
title: cfosspeed基本设置 
date: 2021-03-01 10: 05: 23
categories:
- 2021-03
tags:
- cfosspeed
---
<center>cfosspeed基本设置 </center>

<!-- more -->

## 方法一：自动校准
右击任务栏图标——流量调整——线路校准，等过几天会自动调整到满状态。
## 方法二：手动校准
1. 同样进行线路校准操作
2. 打开[测速网](https://www.speedtest.cn/)，记住最大下载速度和最大上传速度以及最后显示的值（即为稳定速度）。
2. 右击任务栏图标——流量调整——打开cfosspeed控制台，输入以下命令
 ```bash
 spd speed # 查看速度情况，我们需要将calibrated一项调整到100，但是调不到也没有必要强求
 spd set maxtxraw=最大下载速度
 spd set maxtxacked=稳定下载速度
 spd set maxrx=最大上传速度
 spd set tx_bounce_cnt=5
 ```
 运行完上述命令后可以再次输入spd speed可以看到calibrated一项已经为100或者十分接近100.