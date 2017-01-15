---
title: "Decrypt9 (Homebrew Launcher)"
permalink: /decrypt9-(homebrew-launcher).html
---

因为有一个bug，safehax需要一个能正常工作的卡带（3ds，nds，烧录卡等）插入机器才能成功。作为一个临时解决方案，系统版本在9.2.0及以下的用户可以无需卡带，直接拷贝Decrypt9WIP.3dsx到/3ds/下，无需破解即可运行。
{: .notice--info}

#### 你需要森么

* 最新版的 [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/)
* 最新版的 [safehax](https://github.com/TiniVi/safehax/releases/latest)
* 最新版的 [fasthax](https://github.com/nedwill/fasthax/releases/latest)

#### 指导

1. 在SD卡根目录创建`files9`目录（如果不存在）
2. 复制`safehax.3dsx`文件到SD卡的`/3ds/`目录下
3. 复制`fasthax.3dsx`文件到SD卡的`/3ds/`目录下
3. 复制Decrypt9WIP压缩包中的`Decrypt9WIP.bin`文件到你SD卡根目录下，重命名为`safehaxpayload.bin`
4. 机器插入SD卡
5. 进入homebrew launcher
7. 运行fasthax
8. 运行结束后，按(Start)键退出，返回到homebrew launcher
  + 可能需要多试几次
9. 运行safehax
10. 如果利用漏洞成功，你将进入Decrypt9

请前往[2.1.0 ctrtransfer](2.1.0-ctrtransfer.html) 
{: .notice--primary}
