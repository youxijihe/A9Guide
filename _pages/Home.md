---
layout: splash
permalink: /
header:
  overlay_color: "#5e616c"
  overlay_image: home-page-feature.jpg
  overlay_filter: 0.5
  cta_label: "开始"
  cta_url: "/get-started"
  caption:
excerpt: '一个详细阐述3ds自定义固件的向导, <br /> 从陈旧的破解方式转向arm9loaderhax。<br />'
---

**要使用这个向导中的[torrent](https://en.wikipedia.org/wiki/Torrent_file)文件，你需要[迅雷](http://www.xunlei.com)或者[百度网盘](http://pan.baidu.com)离线下载功能，当然向导也提供网盘下载**
{: .notice--info}

**在继续之间请认真阅读以下的介绍知识**
{: .notice--warning}

## 什么是Homebrew?

[**Homebrew**](https://en.wikipedia.org/wiki/List_of_homebrew_video_games) 通常来说是只未经任天堂许可的软件。它允许你运行homebrew游戏,一些用来编辑和备份存档的工具， 或者是一些旧系统的模拟器。

通常,在你的主机上运行homebrew是100%免费的，你只需要通过浏览器就可以。但也有一些其它漏洞是在商业游戏中的，你需要这些游戏才能让homebrew跑起来.

## 什么是自定义固件?

**自定义固件** ("CFW") enables you to use more advanced hacks that userland homebrew can't easily do. For instance, signature patches let you install unsigned titles that appear right on your HOME Menu.

CFW 能够很容易的在9.2.0-20或以下的主机中安装。其它版本能够通过降版本，大部分是免费的，最差也只需一个有漏洞的游戏。

## 这个向导是用来安装什么的?

This guide has the end goal of taking a completely unmodified 3DS from stock
firmware to arm9loaderhax powered Custom Firmware. On some versions, it utilizes homebrew as a jumping off point, but Custom Firmware is still the goal.

Arm9loaderhax is the newest and best method of launching Custom Firmware that gives us nearly full control of the system only milliseconds into boot, which is similar to the effect of BootMii for the Wii.

The benefits of arm9loaderhax over other Custom Firmware launch methods are numerous, and as such it is recommended to use this guide over any other that relies on outdated software (such as menuhax or rxTools).

## 使用自定义固件我能干啥?

+ 无视锁区，畅玩所有卡带游戏和eShop游戏
+ Customize your HOME Menu with user-created [themes](https://3dsthem.es/) and [badges](https://badges.3dsthem.es/)
+ Use "ROM hacks" for games that you own
+ Take gameplay and application screenshots
+ [Backup, edit, and restore](https://gbatemp.net/threads/release-jks-savemanager-homebrew-cia-save-manager.413143/) saves for many games
+ Play games for older systems with various emulators, using RetroArch or other standalone emulators. (Works best with a New Nintendo 3DS)
+ Install homebrew titles to your system, and have them appear on your HOME Menu
+ Dump your game cards to a format you can install, and play them without needing the card
+ New 3DS only: stream live gameplay to your PC wirelessly with NTR CFW
+ Run many old Nintendo DS flash carts that were blocked long ago or never worked on Nintendo 3DS
+ Safely update to the latest system version without fear of losing access to homebrew

## 在开始之前你需要知道什么?

+ **在开始之前，你必须知道破解的风险： EVERY time you modify your system, there is always the potential for an UNRECOVERABLE brick. They're rare, but still a possibility so make sure you follow ALL directions EXACTLY.**
+ If you have already hacked your 3DS before to get an EmuNAND setup, and would like to move the contents of your previous EmuNAND to your new SysNAND CFW, you should follow all instructions and restore your existing EmuNAND when prompted once you reach [Installing arm9loaderhax](installing-arm9loaderhax).
+ This guide will work on New 3DS, Old 3DS, and 2DS in all regions on firmware 11.2.0 or below *(except CHN / TWN on both New 3DS and Old 3DS, and KOR New 3DS)*.
+ If everything goes according to plan, you will lose no data and end up with everything that you started with (games, NNID, saves, etc will be preserved).
+ A large part of this guide is lengthy NAND dumps and downgrades, so the entire process can take *several* hours thanks to the 3DS's slow processor.
+ **Keep the device plugged in and charged throughout the entire process to avoid data loss or damage from an unexpected power-off!**
+ Your SD card should be [MBR, not GPT](http://www.howtogeek.com/245610/) (the SD card that comes with the device will be MBR by default).
+ If you need to format a brand new SD card, you can use [`guiformat`](http://www.ridgecrop.demon.co.uk/index.htm?guiformat.htm) and set to an Allocation Unit Size of 32K.
+ The 2DS is essentially identical to the Old 3DS in terms of software, and that any steps which say "Old 3DS" also apply to 2DS.
