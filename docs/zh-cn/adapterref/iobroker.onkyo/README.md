---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.onkyo/README.md
title: ioBroker.onkyo
hash: 0UrlqHs+CqpyKdo8oX1S7jFJE940wg34/Nco0GC6/nE=
---
![商标](../../../en/adapterref/iobroker.onkyo/admin/onkyo.png)

![安装数量](http://iobroker.live/badges/onkyo-stable.svg)
![NPM版本](http://img.shields.io/npm/v/iobroker.onkyo.svg)
![资料下载](https://img.shields.io/npm/dm/iobroker.onkyo.svg)
![特拉维斯](https://travis-ci.org/ioBroker/ioBroker.onkyo.svg?branch=master)
![NPM](https://nodei.co/npm/iobroker.onkyo.png?downloads=true)

＃ioBroker.onkyo
###重大更新！
照顾好这个重大更新。从2.0版开始，结构发生了变化！如果您更新到此版本，则必须在任何其他适配器（如VIS或javascript）中更改变量！新版本支持“材料”和“封面艺术”。媒体对象支持播放器窗口小部件，例如sonso或winamp。
![可视化](../../../en/adapterref/iobroker.onkyo/admin/player.png)

该适配器允许使用EISCP协议控制Onkyo和Pioneer AVR。

它使用node-eiscp：https://github.com/tillbaks/node-eiscp

为了发送命令，有一个特殊的状态“ RAW”。仅将RAW命令（例如已知的EISCP Excel文件）写入该状态作为EISCP RAW命令的示例，形式为“ PWR01”。

适配器维护的另一个特殊状态是“已连接”。这是一个布尔值，显示node-eiscp当前是否已连接到接收器。

VIS视图示例![可视化](../../../en/adapterref/iobroker.onkyo/admin/onkyo-vis.png)

##经过测试的接收器
### Onkyo
* TX-NR 525
* TX-NR 626
* TX-NR 727

###先驱
* VXS-S520D
* VSX-1131

<！-下一个版本的占位符（在该行的开头）：

### __进展中__->

## Changelog
### 2.0.5 (2021-04-27)
* (Diginix) fixed some object properties
* (bluefox) Added the support of compact mode

### 2.0.3   
* (Eisbaeeer) now support zone3   

### 2.0.2
* (Eisbaeeer) fix double .js 

### 2.0.0
* (Eisbaeeer) Major update iobroker.onkyo

### 1.1.5
* (Eisbaeeer) Zones will be powered if tune preset selected   

### 1.1.4  
* (Eisbaeeer) Added direct tuning in zones (issue #2)

### 1.1.3
* (Eisbaeeer) Adding Navigation Items   

### 1.1.2
* (Eisbaeeer) Adding CoverArt

### 1.1.1
* (Eisbaeeer) Update zone 2 volume after power on. Adding Pioneer Receivers with eiscp support.

### 1.1.0
* (Eisbaeeer) Completely new structure (Zone1, Zone2, Device)

### 1.0.5
* (Eisbaeeer) Changed structure
* (Eisbaeeer) Added Object RAW to send own commands

### 1.0.4 (2018.07.24)
* (Eisbaeeer) Cleaned program
* (Eisbaeeer) Fix logging

### 1.0.2 (2018.02.28)
* (Eisbaeeer) Changed name of adapter
* (Eisbaeeer) Added testing of adapter in travis

### 1.0.0 (2017.11.28)
* (Eisbaeeer) Add max volume settings to zone1 and zone2.   
* (Eisbaeeer) changed objects to switch
* (Eisbaeeer) moved adapter to "multimedia"
* (Eisbaeeer) cleaned log outputs

### 0.1.20 (2016.03.29)
* (Eisbaeeer) Add checkbox in settings for VIS objects. Volumes can be set in
  decimal. Power states, mute states, etc. are now usable with VIS buttons.

### 0.1.12 (2016.02.25)
* (installator) Fix power state

### 0.1.11 (2016.01.13)
* (installator) Fix regexp error

### 0.1.10
* (installator) For command CTL sets Center Level -12 - 0 - +12

### 0.1.9
* (installator) change power to system-power

### 0.1.8
* (installator) fix values to control power and enable using of 1 and 0

### 0.1.7
* (bluefox) fix creation of specific states (twice)

### 0.1.6
* (bluefox) fix creation of specific states

### 0.1.5
* (bluefox) fix node-eiscp package

### 0.1.4
* (bluefox) add debug outputs

### 0.1.1
* (bluefox) replace git with tarball

### 0.1.0
* (bluefox) update adapter for new concept

### 0.0.4
* (owagner) use verify_commands=false, to be able to send high-level commands to unknown AVR models

### 0.0.3
* (owagner) allow setting of states other than "command". This will trigger a high level
  command with the state name being set to the new value. Note that this will fail for
  many newer models, as they are not yet properly represented in node-eiscp's
  command table. Use the raw command in that case
* send some initial queries upon connect to get basic state information from the AVR

### 0.0.2
* (owagner) support node-eiscp's Autodiscovery mechanism
* (owagner) updated README, notably removing bogus reference to single instancing

### 0.0.1
* (owagner) initial version

## License
The MIT License (MIT)
Copyright (c) 2019 Eisbaeeer <eisbaeeer@gmail.com>, owagner