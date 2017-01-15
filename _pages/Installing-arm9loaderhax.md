---
title: "安装 arm9loaderhax"
permalink: /installing-arm9loaderhax.html
---

这个向导最终的结果时安装arm9loaderhax和设置Luma3DS让你几毫秒就能启动系统. 这是使用[AuroraWright](https://github.com/AuroraWright/)的SafeA9LHInstaller来完成的.
{: .notice}

这会安装[AuroraWright修改的arm9loaderhax](https://github.com/AuroraWright/arm9loaderhax) .
{: .notice--info}

我们还设置使arm9loaderhax能载入负载(payloads,可以理解为软件)的功能,能让我们通过还原备份拯救变砖的SysNAND分区.
{: .notice--info}

**你不能使用其它设备的OTP否则你肯定变砖。**
{: .notice--danger}


#### 步骤总览

在这个页面，通过各个步骤，最后都是为了: 装上arm9loaderhax.

它可以说是目前最好的设备漏洞，因为它是永久安装到你的NAND固件分区中,运行在系统加载之前, 不但使它能允许运行在*所有*安装的版本上,而且可以保护自己，能在多处情况下从能使非A9LH的3DS变砖的错误主菜单或者坏应用中恢复过来。

这个`arm9loaderhax.bin`文件是arm9loaderhax自己加载了NAND之后载入的,也可以是其他可用的arm9负载(payload）. 这个文件可以任意时间更改,而且Luma3DS允许在启动是按住按键载入其他的arm9负载(playload).

在这里,我们使用[AuroraWright](https://github.com/AuroraWright/) 制作的LUMA直接启动一个打了补丁的SysNAND系统分区,让我们完全不需要任何的EmuNAND虚拟分区, 大幅简化破解3DS的使用，而且节省SD卡空间.

只要arm9loaderhax安装上 ，Luma3DS正常设置，我们可以恢复之前的备份。

在着过程中，我们还会安装下面的常用软件:
+  **FBI** *(安装CIA格式的游戏和应用)*
+  **Luma3DS Updater** *(方便升级自制系统)*
+  **Hourglass9** *(能做NAND和卡带相关功能的多用途工具)*

#### 你需要什么

* [`aeskeydb.bin`](magnet:?xt=urn:btih:18b3a17f78e2376e05feaa150749d9fd689b25dc&dn=aeskeydb.bin&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* [`fbi-2.4.2-injectable.zip`](magnet:?xt=urn:btih:f978b4cf5eda72823240b9c649f3fd2940a9f525&dn=fbi-2.4.2-injectable.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* [`data_input_v3.zip`](magnet:?xt=urn:btih:a1195c9f7ab650fa7c7bf020b51fc19ea8d9440c&dn=data%5Finput%5Fv3.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* 以上文件可以到网盘下载[度娘盘](https://pan.baidu.com/s/1i52q4Ax) 密码:uum9
* 最新改版的[SafeA9LHInstaller](https://github.com/Plailect/SafeA9LHInstaller/releases/latest) *（`.7z`文件）*
* 最新版的 [arm9loaderhax](https://github.com/AuroraWright/arm9loaderhax/releases/latest)
* 最新的[Luma3DS](https://astronautlevel2.github.io/Luma3DS/builds/Luma-1eb18c17.zip) *（`.7z`文件）*
* 最新版的 [hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases/latest)
* 最新版的 [Hourglass9](https://github.com/d0k3/Hourglass9/releases/latest)
* 最新版的 [Luma3DS Updater](https://github.com/Hamcha/lumaupdate/releases/latest)
* 最新版的 [DspDump](https://github.com/Cruel/DspDump/releases/latest)
* 最新版的 [FBI](https://github.com/Steveice10/FBI/releases/lastest)
* 最新版的 [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* Homebrew Launcher[Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)

#### 指导

##### 第 I 步 - 准备工作

{% capture notice-5 %}
**确保你的SD没有损坏!**

**如果你使用损坏的卡，有可能变砖头!**

**如果觉得SD卡有可能损坏了,可使用这些工具检测[H2testw (Windows)](h2testw-(windows).html), [F3 (Linux)](f3-(linux).html), or [F3X (Mac)](f3x-(mac).html)!**
{% endcapture %}

<div class="notice--danger">{{ notice-5 | markdownify }}</div>

1. **如果SD卡存在`/files9/`目录，请将`/files9/`目录拷贝到安全的地方; 最好多几个地方备份（比如网盘）; 如果你在将来出错，这个备份可以拯救你，避免数据丢失**
2. 在sd卡根目录创建`cias` 目录（如果不存在）
4. **删除SD卡根的`a9lh`目录（如果存在）**
  + **如果你安装arm9loaderhax意外地使用了其他设备的`OTP.bin`, 3DS将变成砖头!**
3. 删除SD卡根目录的`3ds`目录（如果存在）
4. **将`starter.zip`解压后的内容复制到SD卡根目录**
  + 你会重新有一个新的`3ds`目录替代你刚删除的
5. 将SafeA9LHInstaller.7z文件解压后的内容复制到SD卡根目录
6. 复制 `data_input_v3.zip`中的 `a9lh`目录到SD卡根目录
7. 将arm9loaderhax 发布的zip包解压后的内容复制到SD卡的`a9lh`目录
9. 复制 hblauncher_loader zip 文件中的`hblauncher_loader.cia`到SD卡`/cias/`目录
10. 复制 Luma3DS Updater zip 文件中的`lumaupdater.cia`到SD卡`/cias/`目录
11. 复制 FBI zip文件中的 `FBI.cia`到SD卡`/cias/`目录
12. **解压Luma3DS压缩包，将`out`文件夹中的`arm9loaderhax.bin`到SD卡根目录,覆盖已存在的文件**
13. 在SD卡根目录创建`luma` 目录
14. 在SD卡`luma`目录下创建`payloads` 目录
15. 复制Hourglass9 zip文件中的 `Hourglass9.bin`到SD卡上的`/luma/payloads`目录中，然后重命名成`start_Hourglass9.bin`
15. 解压GodMode9压缩包，复制`GodMode9.bin`到你SD卡的`/luma/payloads/`目录下，并重命名`GodMode9.bin`为`up_GodMode9.bin`
16. 复制 `aeskeydb.bin` to 到SD卡`/files9/`目录
17. 复制 `DspDump.3dsx` to 到SD卡`/3ds/`目录
18. 将`fbi-2.4.2-injectable.zip`解压后的内容到SD卡`/files9/`目录
19. 清除主菜单的主题数据（Home Menu's extdata）: `/Nintendo 3DS/(32个字母长度的ID)/(32个字母长度的ID)/extdata/00000000/`
       + EUR Region 欧版: 删除 `00000098`
       + JPN Region 日版: 删除 `00000082`
       + USA Region 美版: 删除 `0000008f`
       + CHN Region 国行: 删除 `000000A1`
       + KOR Region 韩国: 删除 `000000A9`
       + TWN Region 台版: 删除 `000000B1`

##### 第 II 步 - 安装arm9loaderhax

1. 插上SD卡
2. 按下面步骤安装arm9loaderhax:
  + 你应该在 2.1.0版本上
  + 在3DS浏览器进 `http://dukesrg.github.io/2xrsa.html?arm11.bin`
    + 如果出错, [请看故障检测指导](troubleshooting.html#ts_browser)
    + 如果花屏, [请看故障检测指导](troubleshooting.html#ts_safe_a9lh_screen)
  + 按 (Select) 完全安装
  + 安装器在你的设备上会安装arm9loaderhax(这非常快)
  + 关机, 如果必要请长按电源键直到关机
  + 将`/a9lh/`目录中你设备特有的 `OTP.bin` 拷贝到安全的地方; 最好多几个地方备份（比如网盘）,然后重新插上SD卡

##### 第 III 步 - 设置Luma3DS

1. 开机时长按select进入Luma3DS菜单
  + 请在按电源键之前长按start
  + 如果黑屏, [请看故障检测指导](troubleshooting.html#ts_sys_a9lh)   
  + 如果启动到SafeA9LHInstaller, [请看故障检测指导](troubleshooting.html#ts_safe_a9lh)
2. 使用 (A) 按键和十字方向键开启下列选项: 
  + **"Autoboot SysNAND"**
  + **"Use SysNAND FIRM if booting with R (A9LH)"**
  + **"Show NAND or user string in System Settings"**
3. 如果你使用 **New 3DS**, *还可以* 开启下面的选项:
  + **"New 3DS CPU" to "Clock+L2(x)"**
    + 这个增加游戏的帧率，但有些可能造成有些游戏不稳定
    + 如果游戏不行,请关闭这个选项
4. 按Start保存然后重启
  + 如果你黑屏，请继续往下走  

##### 第IV步 - 恢复系统

在看跟随这个指导之前，如果你已经有做过EmuNAND（虚拟系统）为基础的自定义固件,想要将之前EmuNAND（虚拟系统）中的内容移到新的SysNAND系统中
是时候跟随[这个向导转移EmuNAND](move-emunand.html)，替代这一章节的第一步
{: .notice--info}


1. 启动是按住(Start)通过arm9loaderhax打开Hourglass9
2. 进入 "SysNAND Backup/Restore"
3. 从 `NANDmin.bin` 恢复
4. 按(Start) 重启
  + 如果你黑屏, [请看 9.2.0 ctrtransfer](9.2.0-ctrtransfer.html)
5. 如果你的备份是 3.0.0 到 4.5.0之间的, 你的设备不会启动除非手动下载下面的必须固件
  + 下载 [这个文件](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/00000056) 重命名为 `firmware.bin`
  + 下载 [这个文件](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/cetk)
  + 复制 `firmware.bin` 和 `cetk` 到SD卡`/luma/`目录
  + 更新你的3DS后，删除上面的这两个文件
6. 进入系统设置, 选第四个 "其他设置",然后到最右边选"系统升级"来升级你的系统
  + 使用A9LH + Luma（或其它CFW）是安全的
  + 不要升级New 3DS2.1.0版本的警告并不适用于恢复NAND备份之后
  + 如果出错，设置 DNS为自动（"auto"）。如果网络出错，请重试几次，或者半夜再更新
  + 如果还是出错并且你的NAND是9.2.0以下, [请看 9.2.0 ctrtransfer](9.2.0-ctrtransfer.html)


##### 第V步 - 注入 FBI

1. 启动是按住(Start)通过arm9loaderhax打开Hourglass9
2. 进入 "SysNAND Backup/Restore", 然后选择 "Health&Safety Dump" 选项将Health & Safety导出成 `hs.app` **(你可以用 上下 / 左右 改变文件名)**,按A确定导出。
3. 然后按 (B), 返回选择"Health&Safety Inject"
8. 选择符合你区域的 注入用的FBI `.app`
4. 按(A)确定注入
9. 按(Start) 重启
10. 你之前是用Gateway降级过，下一章第一步依然进入的还是原版的Health & Safety应用, [请看故障检测指导](troubleshooting.html#gw_fbi)

##### 第VI步 - 完成设置

2. 打开 Health and Safety (现在是FBI)
3. 选 "SD"
4. 选 "cias"
5. 选择 `FBI.cia` 按(A)安装
6. 选择 `hblauncher_loader.cia`按(A)安装
7. 选择 `lumaupdater.cia` 按(A)安装
8. 选择 `arm9loaderhax.bin`, 按(A) 然后选择 "Copy" 复制选项
9. 按（B）返回FBI主菜单
10. 选 "CTR NAND"
11. 选 "\<current directory>"
12. 选 "Paste"粘贴,  按(A)确定
8. 按HOME退出FBI
9. 从主菜单载入Homebrew Launcher（如果进不去，请更新[boot.3dsx](https://smealum.github.io/ninjhax2/boot.3dsx)文件）
10. 选 "DSP Dump"
11. 按 (Start) 然后确定退出
12. 启动时按住(Start)通过arm9loaderhax打开Hourglass9
13. 进入 "SysNAND Backup/Restore", 然后选 "Health&Safety Inject"
14. 选择 `hs.app` (之前你导出来的不含FBI的), 按(A)确定注入
15. 在主菜单按 (Select)弹出SD卡
15. 在SD移除的情况下按 (Start)重启 
  + 至少在SD移除的情况下启动一次设备，可以让你配置安装了luma的CTRNAND
16. 使用 (A) 按键和十字方向键开启下列选项:    
  + **"Show NAND or user string in System Settings"**
3. 如果你使用 **New 3DS**, *还可以* 开启下面的选项:
  + **"New 3DS CPU" to "Clock+L2(x)"**
    + 这个增加游戏的帧率，但有些可能造成有些游戏不稳定
    + 如果游戏不行,请关闭这个选项
14. 插上SD卡, 按Start保存然后重启

___

如果DSi / DS 功能损坏 (如果DS 卡或DSiWare没法使用), [请看故障检测指导](troubleshooting.html#twl_broken)
{: .notice--warning}

{% capture notice-10 %}
你现在只需打开Luma3DS Updater按(A)就可以更新Luma3DS到最新版 
这个系统更新不是一回事; 这只是下载解压一些最新的Luma3DS文件. Luma3DS Updater只是更新SD卡上的文件
只是更新SD卡上的Luma3DS文件，如果你的无SD卡启动，他会使用你放在CTR NAND中的任何版本.    
{% endcapture %}

<div class="notice--info">{{ notice-10 | markdownify }}</div>

{% capture notice-6 %}   
默认载入基于SysNAND的自定义固件.    
你可以启动时按住 (Select) Luma3DS 配置菜单.    
你可以启动时按住 (Start) 载入Hourglass9,（一个arm9loaderhax的NAND和卡带工具）.     
{% endcapture %}

<div class="notice--info">{{ notice-6 | markdownify }}</div>

在将来，你可以按照这个[更新 A9LH](updating-a9lh.html)指导页面来更新arm9loaderhax
{: .notice--info}

想使用 [NTR CFW](https://github.com/44670/BootNTR/), 在 [这个页面](https://github.com/44670/BootNTR/releases)下载合适的ZIP包， 将`ntr.bin`复制到SD卡根目录, 然后按照从[this](https://github.com/astronautlevel2/BootNTR/releases/latest) 这个页面下载 `BootNTR.cia`安装。
{: .notice--info}

保存好你的`NANDmin.bin`文件,Hourglass9可以利用它来救砖.
{: .notice--info}

如果你已经备份了NAND，你可以删除`/files9/`目录中的备份.
{: .notice--info}

{% capture notice-7 %}
**你可以删除SD卡上*不在*下列表格中的额外文件和文件夹:**

| **SD卡上需要保留的文件和文件夹:** |
|:----------------------------------------------:|
| `3ds` |
| `files9` |
| `hblauncherloader` |
| `luma` |
| `Nintendo 3DS` |
| `arm9loaderhax.bin` |
| `boot.3dsx` |
{% endcapture %}

<div class="notice--info">{{ notice-7 | markdownify }}</div>

如果你需要下载游戏, 可以前往[游戏集合游戏区](https://youxijihe.com/game).
{: .notice--success}

如果你要为你的设备切换区域, 请看[切换区域](region-changing.html) 页面.
{: .notice--success}

你想需要保证你的A9LH安装是最新版, 请看[更新A9LH](updating-a9lh.html) 页面.
{: .notice--success}

想了解如果使用Luma3DS, 请看 [它的wiki（英文）](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage).
{: .notice--success}
