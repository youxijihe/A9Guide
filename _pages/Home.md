---
layout: splash
permalink: /
header:
  overlay_color: "#5e616c"
  overlay_image: home-page-feature.jpg
  overlay_filter: 0.5
  cta_label: "开始"
  cta_url: "/get-started.html"
  caption:
excerpt: '一个详细阐述破解3ds做自定义固件的向导, <br /> 从陈旧的破解方式转向arm9loaderhax。<br />'
---

**要使用这个向导中的[torrent](https://en.wikipedia.org/wiki/Torrent_file)文件，你需要[迅雷](https://www.xunlei.com)或者[百度网盘](https://pan.baidu.com)离线下载功能，当然向导也提供网盘下载**
{: .notice--info}

**在继续之间请认真阅读以下的介绍知识**
{: .notice--warning}

## 什么是Homebrew?

[**Homebrew**](https://en.wikipedia.org/wiki/List_of_homebrew_video_games) 通常来说是指未经任天堂许可的软件。它允许你运行homebrew游戏,一些用来编辑和备份存档的工具， 或者是一些旧系统的模拟器。

通常,在你的主机上运行homebrew是100%免费的，你只需要通过浏览器就可以。但也有一些其它漏洞是在商业游戏中的，你需要这些游戏才能让homebrew跑起来.

## 什么是自定义固件?

**自定义固件** ("CFW") 能让你做更多的破解，而这些是在用户空间的homebrew很难做到的。 比如，签名补丁能让你安装没有签名过的软件

CFW 能够很容易的在9.2.0-20或以下的主机中安装。其它版本能够通过降版本，大部分是免费的，最差也只需一个有漏洞的游戏。

## 这个向导是用来安装什么的?

这个指导是让一台未破解的机器完全变成一台强大的arm9loaderhax自制系统。在有些版本, 它会用homebrew作为跳出点（jumping off point）, 但是自制固件依然是目标。

Arm9loaderhax是最新最好载入自制系统的方式，能几秒启动并让我们几乎能完全掌控系统，相当于Wii上的BootMii。

相比其他方式，arm9loaderhax 的优势有很多,所以建议依赖过时的软件(such as menuhax or rxTools)的各位按此向导来做更新

## 使用自定义固件我能干啥?

+ 无视锁区，畅玩所有卡带游戏和eShop游戏
+ 利用用户自制的[主题](https://3dsthem.es/)和[图标](https://badges.3dsthem.es/)来个性化你的主菜单
+ 在你拥有的游戏上做"ROM hacks"
+ 游戏应用截屏
+ [备份, 编辑, 和欢迎](https://gbatemp.net/threads/release-jks-savemanager-homebrew-cia-save-manager.413143/) 各种游戏存档
+ 利用旧系统的模拟器，比如RetroArch或其他独立的模拟器来玩老游戏. (新3ds更好)
+ 安装homebrew自制软件到主菜单
+ 从卡带上导出游戏，然后无卡玩耍
+ 只限New 3DS: 利用NTR CFW将游戏串流到你的PC上
+ 运行一些老的被封的或者无法运行的DS烧录卡
+ 安全升级到最新版，不怕失去破解homebrew

## 在开始之前你需要知道什么?

+ **在开始之前，你必须知道破解的风险： 每次你更改系统,都有无法恢复的变砖的可能性。 虽然很少见，但依旧可能会，所以请严格按照步骤来走**
+ 如果你之前已经有做过EmuNAND（虚拟系统）为基础的自定义固件,想要将之前EmuNAND（虚拟系统）中的内容移到新的SysNAND系统中,请确保当你到达[安装 arm9loaderhax](installing-arm9loaderhax.html)这一步的时候，已跟随所有的指导并恢复了你的现存的EmuNAND（虚拟系统）。
+ 此向导使用于11.2.0及以下的New 3DS, 老 3DS, 和2DS  *(除了CHN国行 / TWN台版的New 3DS和老 3DS,还有KOR韩国的New 3DS)*.
+ 如果一切按计划走,你不会丢失任何数据(游戏, NNID, 存档等会保留).
+ 感谢任天堂的垃圾配置，向导的有一大部分是在做NAND导出和降级，所以整个过程可能需要花费*几个*小时。
+ **保持设备充电，避免在整个过程中因为突然没电而造成丢失数据或损坏!**
+ SD卡分区表必须是 [MBR, 不是 GPT](http://www.howtogeek.com/245610/) (SD卡一般默认是MBR).
+ 如果你需要格式化新SD卡, 你可以使用[`guiformat`](http://www.ridgecrop.demon.co.uk/index.htm?guiformat.htm) ，设置分块（Allocation Unit）大小为32k
+ 2DS软件上基本上等于老3DS，所以步骤中提到"老 3DS"的也适用于2DS.
