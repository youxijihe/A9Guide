---
title: "Homebrew Launcher (浏览器)"
permalink: /homebrew-launcher-(browser).html
---

Homebrew Launcher有很多入口和加载的方式。最常用的是browserhax（浏览器破解）, 只需内置浏览器即可载入。
{: .notice--info}

**Browserhax（浏览器破解）只适用用 欧（EUR） / 日（JPN） / 美（USA） / （韩）KOR 区域!**
{: .notice--warning}

#### 你需要什么

+ [`config.zip`](images/config.zip)
+ 适用于3DS版本的[ropbin](https://smealum.github.io/3ds/#otherapp)
+ The Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
+ 可联网的3DS

#### 介绍

#####  I -  准备

1. 将`starter.zip`解压后的内容复制到SD卡根目录
2. 将`config.zip`解压后的内容复制到SD卡的`/3ds/menuhax_manager/`目录中
3. 在sd卡根目录创建`menuhax`目录（如果不存在）
4. 将上面下载的ropbin文件重名为`menuhaxmanager_input_payload.bin`
5. 将`menuhaxmanager_input_payload.bin` 复制进sd卡的`/menuhax/`目录
4. 将SD卡重新卡进3DS

#####  II -  根据版本略过

1. 打开主题菜单（从主菜单左上角进去）,将你的主题切换成其它的任何一个，然后切换回默认。你会初始化出一些必须的主题数据。

**下面步骤只适用于 9.9.0 to 10.6.0**

1. 打开设置（Settings）
2. 将日期设成 `January 1, 2000`
3. 将时间设成 `00:00`
4. 打开浏览器，迅速打开浏览器设置（越快越好）
5. 滑倒底下，迅速初始化数据(或者称清除所有数据（Clear All Save Data）)

##### III -  书签 browserhax

**此节只适用于New 3DS的10.7.0版本**

1. 打开浏览器
2. 在下屏幕左下脚选择书签菜单星号
3. 将第一个书签的URL换成 `http://plail.ueuo.com/3dsbrowserhax_auto.php`
4. 按下完成（Done）, 然后返回主菜单
5. 在下屏左上角选着菜单选项
6. 下拉并选择关闭WIFI连接（Wireless Communication / NFC）
7. 使用电源按钮关闭3DS
8. 打开3DS
9. 使用菜单选项打开wifi连接（Wireless Communication / NFC）
10. 迅速打开浏览器（越快越好）,载入书签
11. 这可能需要重试几次;如果弹出要求你升级，请重启关闭wifi连接，多试几次
12. 这时候你的主机进入了homebrew菜单
13. 忽略第IV节 -  browserhax

##### IV -  browserhax

8. 将浏览器导向 `http://plail.ueuo.com/3dsbrowserhax_auto.php`
    + 你也可以通过扫描QR二维码进入 (在主菜的按 (L + R) ,然后点击下屏的QR二维码图标)     
![browserhax_auto](http://plail.ueuo.com/3dsbrowserhax_auto_qrcode.png)
    + If you get an error, [follow this troubleshooting guide](troubleshooting#ts_browser)
9. 你的主机会进入homebrew菜单

##### V -  menuhax

10. 打开menuhax_manager应用
11. 按(A)安装,也许会出现一些错误信息但是只要最后显示"Install finished successfully"就可以
    + 如果中途提示你是否"override the detected system version," 按(B)取消
12. 返回menuhax_manager的主菜单, 然后选择"Configure menuhax"
13. 按(A)继续，选着"Type1"
14. 按住十字方向的(下)不要松手,安然触摸下屏；这是此向导推荐的用于载入homebrew的按键，因为它和其它工具不冲突。
15. 返回menuhax_manager的主菜单, 按(B), 再按(Start) 退出返回到Homebrew Launcher
16. 按(Start)，再按(A)重启机器 
17. 当系统启动的时候按住十字方向的(下)就可进入Homebrew Launcher

你现在可以通过在启动系统的时候按住十字方向的（下）进入Homebrew Launcher
{: .notice--info}

如果你大于9.2.0, 继续到 [9.2.0 降级](9.2.0-downgrade)
{: .notice--primary}

如果你是 9.2.0或以下, 继续到 [Decrypt9 (Homebrew Launcher)](decrypt9-(homebrew-launcher))
{: .notice--primary}
