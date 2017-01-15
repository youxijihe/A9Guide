---
title: "故障检测"
permalink: /troubleshooting.html
---

如果你没法启动3DS, 请查看你相关的章节，然后按照指引做。一旦问题解决，你可以继续主引导的步骤。
(这一页相当长，请试着用Ctrl+F搜索问题)
{: .notice--primary}

**如果你依然没法解决问题，需要额外的帮助，请你SD卡根目录的所有相关的.log文件内容到[游戏集合](https://youxijihe.com/)社区发帖子求助.**
{: .notice--info}

## <a name="twl_broken" />完成向导后DSi / DS 功能损坏了，没法用了

#### 你需要什么

* 适合你设备的 TWL_FIRM `.cia`
    + [`New_3DS TWL_FIRM - v9936.cia`](torrents/New_3DS%20TWL_FIRM%20-%20v9936.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:eab8558c97b18b1f329a2bfcc3c899b84c082a27"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
    + [`Old_3DS TWL_FIRM - v8817.cia`](torrents/Old_3DS%20TWL_FIRM%20-%20v8817.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:17511eadb6e6f3ff22d04f90644e37bd2d96ca43"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
* [`TWL Version Data - v0.cia`](torrents/TWL%20Version%20Data%20-%20v0.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:4a106681407fede5de95cc8bda635432481f6b5d"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
* [`DS Internet - v2048.cia`](torrents/DS%20Internet%20-%20v2048.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:2b9df8496922f2546dfb0b01220068ce53c19d3d"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
* [`DS Download Play - v1024.cia`](torrents/DS%20Download%20Play%20-%20v1024.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:b581d3c5d98f5e621fddfc1ce5704bb45bf05a8c"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
* [`Nintendo DS Cart Whitelist - v11264.cia`](torrents/Nintendo%20DS%20Cart%20Whitelist%20-%20v11264.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:7b90d506ad032a581a00035616eaa17a68c48eff"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>

#### 指导

##### 第I步 - 准备工作

1. 在sd卡根目录创建`cias` 目录（如果不存在）
1. 复制 `TWL Version Data - v0.cia` 到SD卡的 `/cias/`目录中
2. 复制 `DS Download Play - v1024.cia` 到SD卡的 `/cias/`目录中
3. 复制 `DS Internet - v2048.cia` 到SD卡的 `/cias/`目录中
4. 复制 `Nintendo DS Cart Whitelist - v11264.cia`到SD卡的 `/cias/`目录中
5. 复制 `New_3DS TWL_FIRM - v9936.cia` 或 `Old_3DS TWL_FIRM - v8817.cia` 到SD卡的 `/cias/`目录中

##### 第II步 -安装软件

1. 打开 FBI
3. 选 "SD"
4. 先 "cias"
8. 选 "\<current directory>"
9. 选 "Install and delete all CIAs"
8. 用home按钮退出

## <a name="rm_nnid" />不格式化移除NNID

#### 你需要什么

* 最新版的 [GodMode9](https://github.com/d0k3/GodMode9/releases/)

#### 指导

1. 复制GodMode9 zip文件中的`GodMode9.bin`到SD卡上的`/luma/payloads`目录中，然后重命名成`up_GodMode9.bin`
6. 重启时按住(十字键上) 打开GodMode9
14. 进入 `SYSNAND CTRNAND` -> `data` -> (32 字符长度的ID) -> `sysdata` -> `00010038`
15. 按住(R)按钮, 在`00000000`上按X重命名文件
16. 放开R重名为 `10000000`
17. 按 (A)保存更改
18. 按(A)解锁SysNAND写功能,然后按要求按组合键
18. 返回主菜单
16. 按(Start)重启

## <a name="gw_fbi" />在用Gateway降级的设备上没法注入H&S
这是因为Gateway用了一个很劣质的降级方式, 会在系统中遗留下两个不同版本的软件. 有一个是没用的,但是会干扰Decrypt9, 使它注入到错误的那一个上.

#### 你需要什么

* 最新版的 [GodMode9](https://github.com/d0k3/GodMode9/releases/)

#### 指导

1. 复制GodMode9 zip文件中的`GodMode9.bin`到SD卡上的`/luma/payloads`目录中，然后重命名成`up_GodMode9.bin`
2. 插上SD卡
5. 重启时按住(十字键上) 打开GodMode9     
2. 进入 `SYSNAND CTRNAND` -> `title` -> `00040010`
7. 进入到你设备和区域的目录中:
  + **老 3DS EUR 欧版**: `00022300` -> `content`
  + **老 3DS JPN 日版**: `00020300` -> `content`
  + **老 3DS USA 美版**: `00021300` -> `content`
  + **New 3DS EUR 欧版**: `20022300` -> `content`
  + **New 3DS JPN 日版**: `20020300` -> `content`
  + **New 3DS USA 美版**: `20021300` -> `content`
8. 注意这里有两对app和tmd文件, 一对以大写为后缀名 (`.TMD` 和 `.APP`), 另一对以小写为后缀名 (`.tmd` 和 `.app`)
11. 按住(R)按钮, 按 (Y)创建新文件夹
10. 按 (A) 确认名字`newdir` (不管叫啥都没关系)
6. 按(A)解锁SysNAND写功能,然后按要求按组合键
9. 在大写文件(`.TMD` 和 `.APP`) 按(L)标记它们
10. 按(Y)复制
11. 进入`newdir`
12. 按 (Y) 粘贴
13. 选择"Move path(s)"
14. 大写的文件就移到`newdir`目录里了
15. 按(Start)重启
16. 返回[安装 arm9loaderhax](installing-arm9loaderhax.html) and retry the FBI injection
17. 如果还是不行,就移到大写的文件移回到 `content` 目录,将小写的移到`newdir`中, 再返回 [安装 arm9loaderhax](installing-arm9loaderhax.html) and 再重试 FBI注入

## <a name="ts_browser" />浏览器相关的漏洞不起作用
浏览器相关的漏洞 (比如 browserhax 或 2xrsa)经常不稳定，频繁崩溃, 有时候可以通过下面几步来解决b

1. 打开浏览器, 打开浏览器设置
    1. 滚到底下然后初始化数据（Initialize Savedata） (或者叫Clear All Save Data)
    2. 再重试

## <a name="ts_safe_a9lh" />系统启动直接进了SafeA9LHInstaller
你复制了错误的 `arm9loaderhax.bin`文件到SD卡里(你只需复制 SafeA9LHInstaller zip文件中的`3ds`目录和 `SafeA9LHInstaller.dat`文件) 

1. 使用正确的 `arm9loaderhax.bin`
    1. 从Luma3DS 压缩文件中复制 `arm9loaderhax.bin`到SD卡根目录
    2. 按住select重启

## <a name="ts_safe_a9lh_screen" />SafeA9LHInstaller显示一个有躁点的屏幕
这偶尔发生,原因未明.按钮可以用，但屏幕看起来除了小毛病

1. 按照常规步骤
    1. 按 (Select) 然后arm9loaderhax会被安装上
    2. 设备会重启
        + 如果不重启,等10秒,然后按住电源键强制关机

## <a name="ts_steelhax" />系统传输steelhax后，目标3DS黑屏

这是因为你选错了了steelhax安装器版本.

1. 下载对应 **目标3DS（第二台）** 版本的 [otherapp payload](https://smealum.github.io/3ds/#otherapp) 
    + 忽略“the NFIRM being downgraded”信息
    + 使用设置中显示的版本
2. 将“otherapp payload”重命名为`steelhax_payload.bin`
3. 复制 `steelhax_payload.bin` 复制到**目标3DS**的SD卡根目录
    + 覆盖任何已有的文件
4. 当载入 **Steel Diver: Sub Wars**的时候按住 (B) 

## <a name="ts_dsiware" />完成DSiWare降级后，我破解过的DSiWare不能正常工作

1. 按住(Start)键重启**来源3DS**，运行Hourglass9
2. 进入“SysNAND Backup/Restore”选项，从`NANDmin.bin`恢复SysNAND（在进行系统转移之前做的备份）
3. 如果在**目标3DS**上没有看到任何游戏，将**目标3DS**与你买游戏用的NNID绑定，尝试重新下载该游戏
  + 你可能需要先从"System Settings（系统设置）" - "Data Management（数据管理）"中先将该游戏删除
  + 如果**目标3DS**不是最新版本的操作系统，你可能需要运行ctr-httpwn才能访问eShop
4. 在**来源3DS**上，执行存档和".app"（如果你正在使用`.app`页面）注入步骤
5. 在**来源3DS**上，依次进入"System Settings（系统设置）" - "Data Management（数据管理）" - "DSiWare"，将你的DSiWare游戏复制到SD卡上
6. 将**来源3DS**的SD卡插入**目标3DS**；或者将**目标3DS**SD上的`Nintendo 3DS`文件夹重命名，然后将**来源3DS**SD卡上的`Nintendo 3DS`文件夹复制到**目标3DS**的SD卡上
7. 在**目标3DS**上，依次进入"System Settings（系统设置）" - "Data Management（数据管理）" - "DSiWare"，将DSiWare游戏复制回系统
8. 将SD卡复原，继续进行DSiWare降级

## <a name="ts_d9_backup" />Decrypt9 或Hourglass9 无法还原/ 找不到我的NAND备份

1. 确保在SD卡**根目录**没有叫"Decrypt9"的目录
3. 试着使用工具检测你的SD卡 [H2testw (Windows)](h2testw-(windows).html), [F3 (Linux)](f3-(linux).html), or [F3X (Mac)](f3x-(mac).html)
4. 试着备份卡上的所有数据,然后格式化再复制回去
5. 试着换一张SD卡

## <a name="ts_sys_down" />启动SysNAND黑屏

1. 尝试将SD卡拿出后启动系统，启动完成后将SD卡插回。
   1. 长按电源键关闭你的3DS。
   2. 拔出你的SD卡。
   3. 启动3DS。
   4. 桌面菜单出现后，插回SD卡。
   5. 如果不行, 应该清除主菜单的主题数据（Home Menu's extdata）: `/Nintendo 3DS/(32个字母长度的ID)/(32个字母长度的ID)/extdata/00000000/`
       + EUR Region 欧版: 删除 `00000098`
       + JPN Region 日版: 删除 `00000082`
       + USA Region 美版: 删除 `0000008f`
       + CHN Region 国行: 删除 `000000A1`
       + KOR Region 韩国: 删除 `000000A9`
       + TWN Region 台版: 删除 `000000B1`
1. 试着无卡带 (烧录卡)启动
2. 如果你有一个硬改和NAND备份, 将它刷回.
3. 试着重启到恢复模式，升级系统.

    *你可能不适应于降级到2.1.0的老3DS* 
    **这会使降级到2.1.0的New 3DS变砖头**
    1. 按住电源键强制关机.
    2. 按住 L+R+A+Up.
    3. 按下电源键3DS开机.
    4. 如果进入安全模式，*仅当你有最新固件版本进入HBL的方法，并且能进行降级的情况下*，才升级你的3DS，并再次尝试降级。
4. 你的3DS可能已变砖头. 试着寻求帮助吧.

## <a name="ts_sys_a9lh" />安装arm9loaderhax后启动SysNAND黑屏

1. 确保你有可用的加载器（payload）.
    1. 检测SD卡根目录是否有 `arm9loaderhax.bin` .
2. 试着重置Luma的配置和修正选项
    1. 删除SD卡上的 `/luma/config.bin`
    2. Set your options when it boots
3. 试着加载进 Hourglass9
    1. 在 Luma3DS, 启动时按 Start
4. 试着删除主菜单的主题数据（Home Menu's extdata）
    1. 清除主菜单的主题数据（Home Menu's extdata）: `/Nintendo 3DS/(32个字母长度的ID)/(32个字母长度的ID)/extdata/00000000/`
       + EUR Region 欧版: 删除 `00000098`
       + JPN Region 日版: 删除 `00000082`
       + USA Region 美版: 删除 `0000008f`
       + CHN Region 国行: 删除 `000000A1`
       + KOR Region 韩国: 删除 `000000A9`
       + TWN Region 台版: 删除 `000000B1`
5. 试着无卡带 (烧录卡)启动
8. 如果你之前是通过Gateway降级的, 确保使用最新版的Luma3DS(至少v6.2.3 或更高)
9. 如果你的NAND是 3.0.0 到 4.5.0之间的, 请看这里:
    + 确保你使用的是最新版的Luma3DS（版本号在v6.6及以上）
    + 下载 [这个文件](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/00000056) 重命名为 `firmware.bin`
    + 下载 [这个文件](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/cetk)
    + 复制 `firmware.bin` 和 `cetk` 到SD卡`/luma/`目录
    + 更新你的3DS后，删除上面的这两个文件
9. 试着参考[9.2.0 ctrtransfer](9.2.0-ctrtransfer.html)
10. 上 [游戏集合](https://youxijihe.com)求助.

## <a name="ts_sys_blue" />启动后蓝屏 (bootrom error)

1. 你的设备变砖头了
2. 你需要 [硬改](https://gbatemp.net/threads/414498/) 修复
