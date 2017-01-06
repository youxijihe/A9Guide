---
title: "Decrypt9 (Homebrew Launcher)"
permalink: /decrypt9-(homebrew-launcher).html
---

因为有一个bug，safehax需要一个能正常工作的卡带（3ds，nds，烧录卡等）插入机器才能成功。作为一个临时解决方案，系统版本在9.2.0及以下的用户可以无需卡带，直接拷贝Decrypt9WIP.3dsx到/3ds/下，无需破解即可运行。
{: .notice--info}

#### 你需要森么

* 最新版的 [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/)
* 最新版的 [safehax+fasthax](/images/safehax-fasthax.zip)

#### 指导

1. 在SD卡根目录创建`files9`目录（如果不存在）
2. 解压safehax+fasthax压缩包，复制其中的文件到你的SD卡根目录，覆盖已有文件
3. 复制Decrypt9WIP压缩包中的Decrypt9WIP.bin文件到你SD卡根目录下，重命名Decrypt9WIP.bin为arm9.bin
4. 机器插入SD卡
5. 进入homebrew launcher
6. 运行safehax
7. 如果漏洞利用成功，你将进入Decrypt9

请前往[2.1.0 ctrtransfer](2.1.0-ctrtransfer.html) 
{: .notice--primary}
