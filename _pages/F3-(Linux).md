---
title: "F3 (Linux)"
permalink: /f3-(linux).html
---

此页引导你使用F3来测试你的SD卡的错误.
{: .notice}

根据容量的大小和电脑的速度,这个过程可能会持续几个小时!
{: .notice--info}

此页只适用Linux用户。如果你不是Linux, 请查看 [H2testw (windows)](h2testw-(windows).html) or [F3X (mac)](f3x-(mac).html) 页面.
{: .notice--info}

#### 你需要什么

* 最新版[F3](https://github.com/AltraMayor/f3/archive/v6.0.zip)

#### 指导

1. 解压f3
2. 使用命令行`cd`到f3目录
3. 执行`make`编译F3（请自行安装编译工具）
4. SD卡插入电脑（或者使用读卡器）
5. Mount SD卡
6. 运行`./f3write <你的sd卡挂载点>`
7. 等待过程完成. 下面是输出例子.

		$ ./f3write /media/michel/6135-3363/
		Free space: 29.71 GB
		Creating file 1.h2w ... OK!
		...
		Creating file 30.h2w ... OK!
		Free space: 0.00 Byte
		Average Writing speed: 4.90 MB/s

8. 运行`./f3read <你的sd卡挂载点>`
9. 等待过程完成. 下面是输出例子.

		$ ./f3read /media/michel/6135-3363/
		                  SECTORS      ok/corrupted/changed/overwritten
		Validating file 1.h2w ... 2097152/        0/      0/      0
		...
		Validating file 30.h2w ... 1491904/        0/      0/      0

		  Data OK: 29.71 GB (62309312 sectors)
		Data LOST: 0.00 Byte (0 sectors)
			       Corrupted: 0.00 Byte (0 sectors)
			Slightly changed: 0.00 Byte (0 sectors)
			     Overwritten: 0.00 Byte (0 sectors)
		Average Reading speed: 9.42 MB/s

如果最好显示 `Data LOST: 0.00 Byte (0 sectors)`, 你的SD卡是好的然后删除卡里的所有`.h2w`文件
{: .notice--success}

如果显示其它信息,你的SD卡或许有坏道或者损坏了，你得换一张了
{: .notice--danger}

返回 [开始干活](get-started.html)
{: .notice--primary}
