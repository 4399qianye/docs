---
title: 使用软件时导致耳机意外关机
---

据反馈，漫步者部分型号的耳机与本软件一起使用时将会导致耳机意外关机。

详情看：
描述错误

使用漫步者EDIFER W200BT经典版 蓝牙耳机，连接笔记本蓝牙播放音乐，在开启 洛雪音乐 时，蓝牙耳机直接关机（正常关机会报语音“关机”，这种情况不会有任何提示）

重现
重现行为的步骤：
1.笔记本（magicbook 2019AMD版+win10pro 1909）连接EDIFER W200BT经典版 蓝牙耳机（据了解不少漫步者蓝牙耳机都有类似情况）
2.开启“洛雪音乐”软件，播放音乐，或 切换歌曲，或其他音量等动作（与蓝牙耳机自动线控相关）
3.此时蓝牙耳机直接关机，无任何提示
4.重新开启蓝牙耳机，连接笔记本后，继续播放，会再次自动关机

预期行为

提供临时关闭高级媒体控制线控的选项，比如新增一个启动参数“-hmkh”，加载如下参数
if (global.envParams.cmdParams.hmkh) app.commandLine.appendSwitch('disable-features', 'HardwareMediaKeyHandling')
我关闭后，暂时只发现无法通过蓝牙耳机控制播放状态（暂停/开始）这个影响，其他软件操作正常

环境：
  -操作系统及版本：[例如：Windows 10 64位 18363.1379]
  -软件安装包及版本：[例如：1.8.0 绿色版]

其他内容

依据之前确认的情况，疑似(漫步者)蓝牙耳机与chrome系列内核的冲突，如chrome浏览器、edge新版浏览器等都会出现类似情况（网页有媒体播放时触发蓝牙耳机关机），可参考zhihu问答如下：
https://www.zhihu.com/question/361141859
针对浏览器的规避方法是在flags页面关闭Hardware Media Key Handling
屏幕截图 2021-03-07 141257
针对electron编写的程序，建议在ready之前加载如下参数关闭对应功能：
app.commandLine.appendSwitch('disable-features', 'HardwareMediaKeyHandling')
参考 #Support chrome 'flags' and all command line options? electron/electron#18253 (comment)
建议将例外运行参数放在软件的设置菜单内，减少用户操作难度

若出现该问题可尝试添加`-dhmkh`启动参数解决，启动参数添加方法请自行百度“windows 给快捷方式添加启动参数”。
