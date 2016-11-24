---
title: "移动EmuNAND"
permalink: /move-emunand.html
---

这是为移动之前的EmuNAND（虚拟系统）中的内容到新SysNAND中，然后删除之前老虚拟系统分区准备的额外章节。注意的是EmuNAND和RedNAND只是[同一个概念](http://3dbrew.org/wiki/NAND_Redirection)略微不同的实现而已.
{: .notice--info}

你会丢失GBA VC 和 DSiWare的存档!
{: .notice--danger}

**你必须已安装了arm9loaderhax + Luma3DS**
{: .notice--danger}

#### 你需要什么

* 已经存在的EmuNAND
* 最新版的 [GodMode9](https://github.com/d0k3/GodMode9/releases/latest)

#### Instructions

1. 复制GodMode9 zip文件中的`GodMode9.bin`到SD卡上的`/luma/payloads`目录中，然后重命名成`up_GodMode9.bin`
2. 3DS重新插上SD卡
3. 启动时按(Start) 通过arm9loaderhax引导进入Hourglass9
4. 进入 "EmuNAND Backup/Restore", 选择"EmuNAND Backup" 选项备份你的EmuNAND到 `NAND_emu.bin`（名字自己选）
5. 按 (B) 返回主菜单
6. 进"SysNAND Backup/Restore", 选"SysNAND Restore (keep a9lh)"选项从`NAND_emu.bin`恢复到你的SysNAND中
7. 按(Select)弹出SD卡
8. SD卡插上电脑, 然后从SD卡的`/files9/`目录中拷贝`NAND_emu.bin.bin`和`NAND_emu.bin.sha` 到安全的地方; 最好多几个地方备份; 如果你在将来出错这个备份可以拯救你 **(你的备份文件的大小需符合 [这个页面](nand-size.html) 的要求; 如果不是，你需要删除重新备份一次!)**
9. 复制好后删除SD卡`/files9/`下的`NAND_emu.bin`和`NAND_emu.bin.sha`文件。
10. **将SD上的所有文件都备份到你的电脑中,接下来的步骤会删除SD卡上的所有文件**
11. 3DS重新插上SD卡
12. 按(Start) 重启，按住(十字键上) 打开GodMode9
13. 按(Home)按钮打开操作菜单(action menu)
14. 选择"SD format menu"
15. 按 (A) 确认
16. 选择 "No EmuNAND"
17. 选择 "Auto"
18. 按照要求输入按键组合确认
19. 按住的 (R) 的同时按下(B)弹出SD卡
16. SD卡插上电脑, 将SD上的之前的所有文件复制回去
18. 3DS重新插上SD卡
19. 按 (A)重新挂载SD卡
20. 按(Start)重启!
19. 如果黑屏, [请看故障检测指导](troubleshooting.html#ts_sys_down)

返回到[安装 arm9loaderhax](installing-arm9loaderhax.html).
