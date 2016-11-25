---
title: "更新A9LH"
permalink: /updating-a9lh.html
---

### 最后更新: 2016.11.3

实际上arm9loaderhax安装是将自己的负载（payload）文件安装到你设备NAND芯片（焊在主板上的）的NFIRM分区, 这个负载很少更新，只是为载入sd卡上的`arm9loaderhax.bin`文件服务。在我们这教程里，是Luma3DS.
{: .notice}

如果你不知道当前安装的是什么版本的arm9loaderhax,只要按步骤安装最新版就行。
{: .notice--info}

如果你的Luma设置了PIN，你需要暂时关掉来完成下面的步骤。你可以完成后打开.
{: .notice--info}

If you are using a payload that does not init the screen on its own (such as Bootanim9), you will need to rename it to `arm9loaderhax_si.bin` instead of `arm9loaderhax.bin`
{: .notice--info}

这一步会更新你的许多负载（payloads） 和AES密钥数据库.
{: .notice--success}

#### 你需要什么

* [`aeskeydb.bin`](torrents/aeskeydb.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:18b3a17f78e2376e05feaa150749d9fd689b25dc"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
* [`data_input_v3.zip`](torrents/data_input_v3.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:a1195c9f7ab650fa7c7bf020b51fc19ea8d9440c"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
* 最新版的 [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest)
* 最新版的 [arm9loaderhax](https://github.com/AuroraWright/arm9loaderhax/releases/latest)
* 最新版的 [SafeA9LHInstaller](https://github.com/AuroraWright/SafeA9LHInstaller/releases/latest)
* 最新版的 [Hourglass9](https://github.com/d0k3/Hourglass9/releases/latest)

#### 指导

**在这些步骤中，在sd卡上覆盖现存的文件.**

##### 第 I 步 - 准备工作

1. 删除sd卡根的`aeskeydb.bin`
4. 删除sd卡根的`a9lh`目录（如果存在）
2. 复制 `aeskeydb.bin` to 到SD卡`/files9/`目录
3. 复制Hourglass9 zip文件中的 `Hourglass9.bin`到SD卡上的`/luma/payloads`目录中，然后重命名成`start_Hourglass9.bin`
5. 将SafeA9LHInstaller zip文件解压，将其中`arm9loaderhax.bin`复制到SD卡`/luma/payloads`目录，重名成`down_safea9lhinstaller.bin`
6. 复制 `data_input_v3.zip`中的 `a9lh`目录到SD卡根目录
7. 将arm9loaderhax的zip包解压后的内容复制到SD卡的`a9lh`目录
8. 复制Luma3DS zip文件中的 `arm9loaderhax.bin`到SD卡根目录,覆盖已存在的文件
9. 3DS重新插上sd卡

##### Section II - 更新负载（Payload）

10. 启动是按住十字键下
11. 按 (Select) 升级arm9loaderhax
12. 关机，将sd卡插到电脑里
13. 删除sd卡根的`a9lh`目录
14. 删除`/luma/payloads`下的`down_safea9lhinstaller.bin`

##### 第 III 步 - 设置Luma3DS

1. 3ds插回sd卡，开机时长按select进入Luma3DS菜单
2. 使用 (A) 按键和十字方向键开启下列选项: 
  + **"Autoboot SysNAND"**
  + **"Use SysNAND FIRM if booting with R (A9LH)"**
  + **"Show NAND or user string in System Settings"**
3. 如果你使用 **New 3DS**, *还可以* 开启下面的选项:
  + **"New 3DS CPU" to "Clock+L2(x)"**
    + 这个增加游戏的帧率，但有些可能造成有些游戏不稳定
    + 如果游戏不行,请关闭这个选项
4. 按Start保存然后重启

##### 第 IV 步 - CTRNAND Luma3DS

16. 打开 FBI
17. 选择 "SD"
18. 移动到 `arm9loaderhax.bin` 上, 按 (A) 选"Copy"复制
9. 按（B）返回FBI主菜单
10. 选 "CTR NAND"
11. 选 "\<current directory>"
12. 选 "Paste"粘贴,  按(A)确定
8. 按HOME退出FBI
9. 3DS关机然后移除SD卡
15. 在SD移除的情况下按住 (Select)重启 
  + 至少在SD移除的情况下启动设备，可以让你配置安装了luma的CTRNAND
16. 使用 (A) 按键和十字方向键开启下列选项:    
  + **"Show NAND or user string in System Settings"**
3. 如果你使用 **New 3DS**, *还可以* 开启下面的选项:
  + **"New 3DS CPU" to "Clock+L2(x)"**
    + 这个增加游戏的帧率，但有些可能造成有些游戏不稳定
    + 如果游戏不行,请关闭这个选项
14. 插上SD卡, 按Start保存然后重启！
