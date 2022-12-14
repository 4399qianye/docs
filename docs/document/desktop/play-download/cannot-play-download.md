---
title: 歌曲无法试听与下载
---

### 通用解决方法

尝试按以下顺序解决：

1. 尝试更新到最新版本
2. 尝试切换其他歌曲（或直接搜索该歌曲），若全部歌曲都无法试听与下载则进行下一步
3. 尝试到 设置-音乐来源 切换到其他接口（一般修改为测试接口就可以解决）
4. 尝试切换网络，比如用手机开热点（所有歌曲都提示请求异常时可通过此方法解决，或等一两天后再试）
5. 若还不行请查看详情：感谢这段时间 Messoer 对本软件提供的音乐数据支持，现因不可抗拒因素 Messoer 已关闭，现已找到其他接口代替，软件内置两个音源，若某个失效可尝试到设置-基本设置切换到另一个试试看。目前音源接口处于不稳定期。
6. 若没有在第 5 条链接中的第一条评论中看到接口无法使用的说明，则应该是你网络无法访问接口服务器的问题，如果接口有问题我会在那里说明。

想要知道是不是自己网络的问题可以看看`http://ts.tempmusic.tk`能不能在浏览器打开，浏览器显示 404 是正常的，如果不是 404 那就证明所在网络无法访问接口服务器。
若网页无法打开或打来不是 404，则应该是 DNS 的问题，可以尝试[修改 DNS 和 HOST](./revise-dns-and-host)

### 提示 `Api is not fond`

尝试修改测试接口

### 歌词为灰色且无法播放

尝试修改测试接口

### 所有歌曲都提示 `请求异常😮，可以多试几次，若还是不行就换一首吧。。。`

尝试更换网络，如切换到移动网络，若移动网络还是不行则尝试开关下手机的飞行模式后再试

若使用家庭网络的话，可尝试将光猫断电 5 分钟左右再通电联网后播放。

### 提示 `getaddrinfo EAI_AGAIN ...` 或 `无法连接到服务器`

尝试在在浏览器打开这个地址`http://ts.tempmusic.tk`，浏览器显示 404 是正常的，如果不是 404 那就证明所在网络无法访问接口服务器。
若网页无法打开或打开来不是 404，则可能是 DNS 的问题，可以尝试上面的方法。

### Windows 版所有歌曲都提示 `音频加载错误，5秒后切换下一首`

尝试关闭 Internet 选项 的代理设置。

如果你不知道怎么做，可以尝试按以下步骤去做：

按<kbd>windows</kbd>+<kbd>r</kbd>键打开“运行”窗口，输入`inetcpl.cpl`后回车，在打开的 Internet 选项 对话框中，切换到 连接 -> 局域网设置，在弹出的新窗口中把代理服务器下的勾去掉，如果自动配置下的勾也有被勾选，那么建议也去掉，最后按确定关闭所有弹窗。

:::tip
如果还是无法解决，那么请更新至最新版再尝试，我们在 1.22.0 的版本中修复了:

`修复若配置了http_proxy环境变量时，会意外使用此代理配置的问题`
:::

> 来源：预期行为：不管什么音乐源播放音乐都显示URL过期，正在刷新URL然后变成音频加载错误，5秒后切换下一首	实际行为：不管什么音乐源播放音乐都显示URL过期，正在刷新URL然后变成音频加载错误，5秒后切换下一首



### 歌曲下载失败，提示 `ENOENT: no such file or directory, mkdir`

更换下载歌曲位置（目录）即可解决（一般是设置的歌曲下载目录没有读写权限导致的）。
