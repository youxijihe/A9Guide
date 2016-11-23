---
title: "Decrypt9 (Homebrew Launcher)"
permalink: /decrypt9-(homebrew-launcher).html
---

这个向导仅仅使用到了SysNAND(真实系统)。如果你之前已经有做过EmuNAND（虚拟系统）为基础的自定义固件，你需要跟随所有在SysNAND中或者适用于SysNAND的操作步骤。注意的是EmuNAND和RedNAND只是[同一个概念](http://3dbrew.org/wiki/NAND_Redirection)略微不同的实现而已.
{: .notice--info}

#### 你需要森么

* 最新版的 [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/)

#### 指导

2. 在SD卡根目录创建`files9`目录（如果不存在）
3. 解压Decrypt9WIP的zip文件，将其中的`Decrypt9WIP`文件夹放到SD卡的`/3ds/`目录下
3. 插入SD卡
4. 进入homebrew launcher
4. 打开Decrypt9WIP **(有时候需要多试几次)**
    + 如果试了多次依然无法进入Decrypt9WIP, 你很有可能是只降级了不完全，需要参考 [9.2.0 Downgrade](9.2.0-downgrade)页面
4. 进入"SysNAND Options", 然后"SysNAND Backup/Restore"
5. 执行"NAND Backup (min size)"，然后用方向键选择一个诸如`NANDmin.bin`的名字按(A)保存
6. 返回主界面

如果你是老3DS, 请前往[2.1.0 ctrtransfer](2.1.0-ctrtransfer) 
{: .notice--primary}

如果你是New 3DS, 按(Start)重启后继续 [安装arm9loaderhax](installing-arm9loaderhax)
{: .notice--primary}
