---
title: "NAND大小和OPT信息"
permalink: /nand-size.html
---

大多少情况下，一个可用的NAND备份是下面大小中的一个
{: .notice--primary}

偶尔,你会备份出跟下面表中不一样的大小。比期望的大是没事的，但请注意*绝不会小于*比下面列着的大小
{: .notice--info}

注意*小容量*的NAND经常会得到小一点的备份。只要符合其中页面中的一个就行.
{: .notice--info}

这些品牌是你设备上NAND芯片的牌子， **不是**你的SD卡。
{: .notice--warning}

**你的备份应该是下面大小中的一个; 如果不是你需要删掉重做!**
{: .notice--danger}

## 2DS:    

    + Toshiba NAND:     
      988.807.168 bytes = 943 MiB    

    + Toshiba NAND:    
      1.979.711.488 bytes = 1.84 GiB    

    + Samsung NAND:    
      1.000.341.504 bytes = 954 MiB    

    + Samsung NAND:    
      1.300.234.240 bytes = 1.21 GiB    

## Old 3DS:    

    + Toshiba NAND:     
      988.807.168 bytes = 943 MiB    

    + Samsung NAND:    
      1.000.341.504 bytes = 954 MiB    

## New 3DS:    

    + Toshiba NAND:    
      1.979.711.488 bytes = 1.84 GiB    

    + Samsung NAND:    
      1.300.234.240 bytes = 1.21 GiB    

    + Samsung NAND:
      1.954.545.664 bytes = 1.82 GiB
      
# OPT信息
      
The OTP is a 0x100 byte region of seemingly random data at address 0x10012000. It is presumed that console unique keys are derived from this region, although it is currently unknown exactly how. The region is likely the console unique data store which is decrypted by the bootrom, but we don't know how that is done until somebody dumps the full protected bootrom. It is unknown at this time if anyone has successfully dumped the protected bootrom.

Prior to version 3.0.0-X, the 0x10012000-region (the OTP) was left unprotected and could be dumped by an attacker with sufficient permissions (arm9 code execution).

After version 3.0.0-X, Nintendo switched to locking this region using the register CFG_SYSPROT9, which also locks the bootloader and is set extremely early in boot, long before we are able to gain code execution. This register can be set exactly once, and cannot be switched off until the unit is fully powered off, and therefore it is impossible to dump the full OTP without a version below 3.0.0-X.

There is, however, a method to dump the hash of the OTP on version 9.6.0-X. Because Kernel9Loader does not clear the SHA_HASH register after it has been used, dumping the SHA_HASH will give the hash of the OTP which was handed over to Kernel9 from Kernel9Loader. In addition, there is a long standing vulnerability where an MCU reboot caused by the i2c will not clear RAM like it's supposed to.

This allows for a hardware based attack where arbitrary data is written to nand_sector96+0x10 in a SysNAND backup and flashed to the device. Afterwards we wire the i2c to MCU reboot on our command, write a payload (which will write 0x1000A040 - 0x1000A060 to a file on the SD card) to arm9 memory somewhere, fill all memory with a NOP sled followed by a JMP instruction pointing to the payload. We can then MCU reboot repeatedly (incrementing nand_sector96+0x10 by 1 each time) until the Kernel9Loader jumps to the payload by random chance.

Because of the complexity and extra hardware involved in the method described above, I have decided to limit the scope of this guide strictly to the software based approach of downgrading to a version below 3.0.0-X. Version 2.1.0-X was selected because it is the only version below 3.0.0-X that contains a fully exploitable browser version (2.0.0-X has a partially exploitable browser, but it won't work for other reasons).

This process involves flashing your CTRNAND to 2.1.0-4. This is accomplished by installing a premade CTRNAND image containing 2.1.0, copying your console specific files (such as `moveable.sed` and `SecureInfo_A`) to it, then fixing the title database CMACS. On New 3DS, it also swaps CTRNAND's encryption slot and installs an Old 3DS NCSD header to NAND, allowing it to boot the Old 3DS only 2.1.0 software.

