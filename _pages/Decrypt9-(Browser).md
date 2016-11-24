---
title: "Decrypt9 (浏览器)"
permalink: /decrypt9-(browser).html
---

这个向导要做的第一件事是让你可以跑Decrypt9, 这是一个可以安装2.1.0版本的多功能工具包。 而2.1.0包含之后我们破解需要利用的漏洞。
{: .notice}

这个向导仅仅使用到了SysNAND(真实系统)。如果你之前已经有做过EmuNAND（虚拟系统）为基础的自定义固件，你需要跟随所有在SysNAND中或者适用于SysNAND的操作步骤。注意的是EmuNAND和RedNAND只是[同一个概念](http://3dbrew.org/wiki/NAND_Redirection)略微不同的实现而已.
{: .notice--info}

#### 你需要什么

* 最新版的[Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/)

#### Instructions

1. 在SD卡根目录创建`files9`目录（如果不存在）
2. 解压Decrypt9WIP的zip文件，将其中的`Launcher.dat` and `Decrypt9WIP.dat`文件放到SD卡根目录下
3. 插入SD卡
4. 在3ds上打开浏览器然后进入下面网址中的一个
    + `https://dukesrg.github.io/?Decrypt9WIP.dat`
    + `http://go.gateway-3ds.com/`
    + `http://www.reboot.ms/3ds/load.html?Launcher.dat`
    + `http://dukesrg.dynu.net/3ds/rop?GW17567.dat&Launcher.dat`
    + 如果第一个没有请试下每一个(有些版本不能用第一个，有些版本不能用后三个)
    + 如果出错, [查看故障检测指南](troubleshooting.html#ts_browser)
5. 如果破解成功,你将载入Decrypt9

继续到 [2.1.0 ctrtransfer](2.1.0-ctrtransfer.html).
{: .notice--primary}
