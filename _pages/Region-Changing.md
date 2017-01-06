---
title: "改变区域"
permalink: /region-changing.html
---

这是改变你arm9loaderhax引导的自制SysNAND系统区域准备的额外章节.通过安装你需要区域的9.2.0 ctrtransfer镜像然后修改SecureInfo_A文件来达成的.
{: .notice--primary}

**因为Luma3DS支持跨区游戏，所以改变区域没有任何必要 [title region emulation](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage).**
{: .notice--info}

本过程将解绑你的NNID和你的系统，因为它们不再兼容。NNID在创建后就会被锁定为当前机器所在的区域，除非经过[一个非常复杂和进阶的流程](https://gist.githubusercontent.com/yifanlu/e80db121d38aceb8cca0e03cefd5853b/raw/3c4dd89869156ca0f945a2791e699acfdb32b510/gistfile1.txt)不能在区域间迁移。
{: .notice--warning}

区域变更后，只有**从未访问过eShop的新3DS**和**任何老3DS**可以在新的区域创建一个新的NNID并访问eShop。已经在原来的区域访问过eShop的新3DS将不能创建一个新的NNID，并在新的区域上访问eShop！
{: .notice--warning}

请注意，有时候eShop在某些本应该可以访问的设备上还是莫名其妙地无法正常访问。这完全取决于任天堂的服务器，我真的背不了这个锅:P
{: .notice--warning}

使用ctr转移进行区域变更（本节教程使用的就是此法）似乎会造成重启补丁失效，原因未知。老3DS用户将无法运行扩展内存模式的游戏（如怪物猎人，任天堂明星大乱斗，和精灵宝可梦日/月）。
{: .notice--warning}

**你必须已经安装了arm9loaderhax + Luma3DS才能进行本节操作。**
{: .notice--danger}

#### 你需要

* 最新版本的[GodMode9](https://github.com/d0k3/GodMode9/releases/)
* 最新版本的[Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/latest)
* 你想更换到的区域的9.2.0 ctr迁移镜像     
  +    [新3DS 9.2.0 - 欧版 - ctrtransfer](magnet:?xt=urn:btih:fed7bfeec0e52b42a77467cfb6ffd3e9dd2d5a70&dn=9.2.0-20E%5Fctrtransfer%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)   
  +    [新3DS 9.2.0 - 日版 - ctrtransfer](magnet:?xt=urn:btih:b22d67fd02b3b0e30ac991e451db0f2d32e7beca&dn=9.2.0-20J%5Fctrtransfer%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    [新3DS 9.2.0 - 美版 - ctrtransfer](magnet:?xt=urn:btih:985d47442dc470d1b9f908256bed041c63885f60&dn=9.2.0-20U%5Fctrtransfer%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)    
~
  +    [老3DS 或 2DS 9.2.0 - 欧版 - ctrtransfer](magnet:?xt=urn:btih:8d6142313971b08f92257e7fb1c1d5689e34ed78&dn=9.2.0-20E%5Fctrtransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    [老3DS 或 2DS 9.2.0 - 日版 - ctrtransfer](magnet:?xt=urn:btih:24ad2b85e67013ef1f91178dca7ad2e40663b9b2&dn=9.2.0-20J%5Fctrtransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  +    [老3DS 或 2DS 9.2.0 - 美版 - ctrtransfer](magnet:?xt=urn:btih:1dc79a2a0babb45497961888f369423a93135e2b&dn=9.2.0-20U%5Fctrtransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)

#### 操作指南

**一些设备只有 `SecureInfo_B` 而不是 `SecureInfo_A`；这是正常现象，使用`SecureInfo_B` 来完成相关的步骤。**    

##### 第一部分 - 准备工作

1. 提取GodMode9压缩包中的`GodMode9.bin`文件，复制到SD卡的`/luma/payloads/`目录下，并将`GodMode9.bin`重命名为`up_GodMode9.bin`
2. 复制`Decrypt9WIP.bin`文件到SD卡的`/luma/payloads/`文件夹，并将`Decrypt9WIP.bin`重命名为`x_Decrypt9WIP.bin`
3. 从ctrtransfer压缩包中提取9.2.0 ctrtransfer文件`.bin`和`.bin.sha`，复制到SD卡的`/files9/` 目录
4. 将SD卡插回3DS

##### 第二部分 - 备份tickets和config save

5. 按住(X)键开机，进入Decrypt9
6. 进入"Ticket/Titlekey Options"，选择"Ticket Dump (SysNAND)"
7. 按(Select)键弹出你的SD卡，并把SD卡插入电脑
8. 删除所有`/files9/`文件夹中**不以**"00-"开头的`.tik`文件
9. 将所有以"00-"开头的`.tik`文件留在文件夹中
10. 重新将SD卡插入你的3DS，并按(B)键返回到主菜单
11. 选择"SysNAND Options"，然后选"System Save Dump"，然后选"Dump configsave.bin"

##### 第三部分 - ctr转移

6. 进入"SysNAND Options"，选择"CTRNAND Transfer"，然后选"Auto CTRNAND Transfer"
7. 按照提示，按(A)键选择9.2.0 ctrtransfer镜像
8. **按照提示，按(A)键备份SysNAND到`NANDmin.bin`**
9. 让迁移过程自动完成，这将耗费一些时间
10. 当迁移过程完成，按(select)键弹出你的SD卡
11. 将SD卡插入电脑，复制`/files9/`文件夹下的`NANDmin.bin`和`NANDmin.bin.sha`文件到一个安全的位置
  + 在多个位置进行备份
  + 备份文件可以在将来出现错误时将你的机器救砖
  + **你的备份文件应该符合[这个](nand-size)页面上列出的大小。如果不是，你应该删除它并重新做一次！**
12. 删除SD卡`/files9/`目录下的9.2.0 ctrtransfer镜像文件`.bin`和`.bin.sha`
13. 将SD卡插回你的3DS

##### 第四部分 - 修改SecureInfo

1. 按住(方向上)键开机，重启进入arm9loaderhax GodMode9
2. 依次选择 `SYSNAND CTRNAND` -> `rw` -> `sys`
3. 找到`SecureInfo_A`，按(Y)键复制
4. 再次按(Y)键粘贴，生成`SecureInfo_A`的副本
5. 选择"Copy path(s)"
6. 按(A)键解锁SysNAND写入权限，接着输入屏幕提示的组合键
7. 选择"Choose new name"
8. 使用十字键重命名文件为`SecureInfo_C`，然后按(A)键完成（覆盖任何已经存在的`SecureInfo_C`文件）
9. 往下翻，找到并选中你刚刚粘贴的`SecureInfo_C`
10. 在`SecureInfo_C`上按(A)键，然后选择"Show in Hexeditor"
11. 按(A)键继续
12. 按(A)键进入编辑模式（edit mode）
13. 将光标移至00000100行的开头并按(A)键
14. 按住(A)键的同时按十字键的上或下来更改数字
15. 根据*你想要变更到的区域*修改00000100行的前两个数字:
    - "00" : 日版
    - "01" : 美版
    - "02" : 欧版
16. 按(B)键退出编辑模式，接着保存更改，然后再按(B)键回到目录
17. 如果一切顺利，你应该在目录中看到`SecureInfo_A`和`SecureInfo_C`这两个文件（Luma3DS在启动时如果检测到`SecureInfo_C`存在，会优先读取`SecureInfo_C`而非 `SecureInfo_A`）
18. 按(Start)键重启

##### 第五部分 - 重装Tickets

1. 打开FBI
2. 选择"SD"
3. 选择"files9"
4. 选择"\<current directory>"
5. 选择"Install and delete all tickets"
6. 等待。系统可能看起来会卡住，多给它一点时间。
7. 按(A)键确认
8. 按(B)键放弃从CDN安装tickets
9. 按home键退出

##### 第六部分 - 区域设置

1. 打开系统设置（System Settings）
2. 依次选择"Other Settings"，"Profile"，"Region Settings"
3. 选择你变更区域后的国家
4. 如果出现提示，无需设置州（state）
5. 将变更区域后的自制系统SysNAND升级到最新版本

##### 第七部分 - 恢复config save

1. 按住(X)键重启，进入Decrypt9
2. 进入"SysNAND Options"，选择"System Save Inject"，然后选"Inject configsave.bin"

老3DS/2DS可能需要格式化机器（使用TinyFormat或系统设置）才能玩扩展内存模式的游戏（如怪物猎人，任天堂明星大乱斗，和精灵宝可梦日/月）。
{: .notice--info}

在进行ctr转移后，*没有恢复config save*就格式化设备，会造成屏幕亮度/闪烁等问题。参见[这里](https://github.com/Plailect/Guide/issues/794)。
{: .notice--info}
