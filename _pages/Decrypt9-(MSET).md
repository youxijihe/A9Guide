---
title: "Decrypt9 (MSET)"
permalink: /decrypt9-(mset).html
---

这个向导要做的第一件事是让你可以跑Decrypt9, 这是一个可以安装2.1.0版本的多功能工具包。 而2.1.0包含之后我们破解需要利用的漏洞。
{: .notice}

这个向导仅仅使用到了SysNAND(真实系统)。如果你之前已经有做过EmuNAND（虚拟系统）为基础的自定义固件，你需要跟随所有在SysNAND中或者适用于SysNAND的操作步骤。注意的是EmuNAND和RedNAND只是[同一个概念](http://3dbrew.org/wiki/NAND_Redirection)略微不同的实现而已.
{: .notice--info}

#### What you need

* 能在你的3DS版本上运行的DS烧录卡 （DS flashcard）
* 最新版的 [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/)

#### Instructions

1. 在SD卡根目录创建`files9`目录（如果不存在）
2. 解压Decrypt9WIP的zip文件，将其中的`Launcher.dat` and `Decrypt9WIP.dat`文件放到SD卡根目录下
3. 插入SD卡
4. 将从Decrypt9WIP的zip文件解压出来的`Decrypt9.nds`放到DS烧录卡上
5. 从你的3DS上启动DS烧录卡
6. 用烧录卡启动`Decrypt9.nds`
7. 根据系统版本选择相应的选项
    + 4.X.X -> "4.x Decrypt9WIP"
    + 6.X.X -> "6.x Decrypt9WIP"
8. 重启系统,进入系统设置，然后"其他选项"（Other Settings），再"用户资料"（Profile）, 然后 "DS软件设定"（Nintendo DS Profile），就是你们瞎叫的414
9. 如果破解成功,你将载入Decrypt9

继续到 [2.1.0 ctrtransfer](2.1.0-ctrtransfer.html).
{: .notice--primary}
