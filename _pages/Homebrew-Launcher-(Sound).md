---
title: "Homebrew Launcher (声音)"
permalink: /homebrew-launcher-(sound).html
---

Homebrew Launcher有很多入口和加载的方式。最新漏洞是soundhax（声音破解）, 无需联网即可载入。
{: .notice--info}

**Soundhax（声音破解）只适用用 欧（EUR） / 日（JPN） / 美（USA） / 区域!**
{: .notice--warning}

#### 你需要什么

1. 适用于3DS版本的[ropbin](https://smealum.github.io/3ds/#otherapp)
2. 适用于3DS版本的[otherapp](https://smealum.github.io/3ds/#otherapp)
3. The Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
3. 可联网的3DS
4. 根据版本下载声音文件
	+ [老3DS-EUR(欧).m4a](images/soundhax-eur-o3ds.m4a)
	+ [老3DS-USA(美).m4a](images/soundhax-usa-o3ds.m4a)
	+ [老3DS-JPN(日).m4a](images/soundhax-jpn-o3ds.m4a)
	+ [New3DS-EUR(欧).m4a](images/soundhax-eur-n3ds.m4a)
	+ [New3DS-USA(美).m4a](images/soundhax-usa-n3ds.m4a)
	+ [New3DS-JPN(日).m4a](images/soundhax-jpn-n3ds.m4a)

#### 介绍

#####  I -  准备

1. 将`starter.zip`解压后的内容复制到SD卡根目录
2. 将符合你机型的`soundhax-xx-x3ds.m4a`声音文件放到SD卡根目录
3. 在sd卡根目录创建`menuhax`目录（如果不存在）
4. 将上面下载的otherapp文件重名为`otherapp.bin`放到SD卡根目录
5. 将上面下载的ropbin文件重名为`menuhaxmanager_input_payload.bin`
6. 将`menuhaxmanager_input_payload.bin` 复制进sd卡的`/menuhax/`目录
7. 将SD卡重新插进3DS

#####  II - 进入HBL
1. 开机后打开自带的 Nintendo 3DS Sound应用(日语叫啥来着，就是那个放音乐的)
2. 等待一会等他载入SD卡, 打开"/SDCARD", 打开"<3 Nedwill 2016"
3. 等待一会你的主机会进入homebrew菜单
	+ 如果如法载入，请确保使用了正确的符合你机型的文件。
	+ 请重新打开Sound应用多试几次。

##### II -  安装menuhax

主题漏洞适用于9.0.0-X - 11.0.0-X，其他版本请忽略

10. 打开menuhax_manager应用
11. 按(A)安装,也许会出现一些错误信息但是只要最后显示"Install finished successfully"就可以
    + 如果中途提示你是否"override the detected system version," 按(B)取消
12. 返回menuhax_manager的主菜单, 然后选择"Configure menuhax"
13. 按(A)继续，选着"Type1"
14. 按住十字方向的(下)不要松手,安然触摸下屏；这是此向导推荐的用于载入homebrew的按键，因为它和其它工具不冲突。
15. 返回menuhax_manager的主菜单, 按(B), 再按(Start) 退出返回到Homebrew Launcher
16. 按(Start)，再按(A)重启机器 
17. 当系统启动的时候按住十字方向的(下)就可进入Homebrew Launcher

如果安装了menuhax，你现在可以通过在启动系统的时候按住十字方向的（下）进入Homebrew Launcher
{: .notice--info}

如果你大于9.2.0, 继续到 [9.2.0 降级](9.2.0-downgrade.html)
{: .notice--primary}

如果你是 9.2.0或以下, 继续到 [Decrypt9 (Homebrew Launcher)](decrypt9-(homebrew-launcher).html)
{: .notice--primary}
