---
title: "改变区域"
permalink: /region-changing.html
---

这是改变你arm9loaderhax引导的自制SysNAND系统区域准备的额外章节.通过安装你需要区域的9.2.0 ctrtransfer镜像然后修改SecureInfo_A文件来达成的.
{: .notice--primary}

**因为Luma3DS支持跨区游戏，所以改变区域没有任何必要，所以就偷懒不翻译了 [title region emulation](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage).**
{: .notice--info}

This process will unlink your NNID from the system, since it will no longer be compatible with it. NNID's are locked to the region of the device that created them, and cannot be transferred between regions without [a very complex and advanced process](https://gist.githubusercontent.com/yifanlu/e80db121d38aceb8cca0e03cefd5853b/raw/3c4dd89869156ca0f945a2791e699acfdb32b510/gistfile1.txt).
{: .notice--warning}

After this process, only **New 3DSs which have never accessed the eShop before** and **any Old 3DSs** will be able to access the eShop after creating a new NNID on their new region. Region changed New 3DSs that have already accessed the eShop on their original region cannot create a new NNID and access the eShop on their new region!
{: .notice--warning}

Note that occasionally the eShop will inexplicably still not work for devices that it should work for. This is entirely to do with Nintendo's servers, and I really do not have any control over it.
{: .notice--warning}

Region changing using ctrtransfer (which this method uses) seems to cause reboot patches to break. The cause for this is unknown, but for now Old 3DS users will be unable to play extended memory mode games (such as Monster Hunter, Super Smash Bros, and Pokémon Sun / Moon).
{: .notice--warning}

**You MUST have already installed arm9loaderhax + Luma3DS to use this.**
{: .notice--danger}

#### What you need

* The latest release of [GodMode9](https://github.com/d0k3/GodMode9/releases/)
* The latest release of [Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/latest)
* The 9.2.0 ctrtransfer image for your device and the region you want to switch to     
  +    [New 3DS 9.2.0 - EUR - ctrtransfer](torrents/9.2.0-20E_ctrtransfer_n3ds.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:fed7bfeec0e52b42a77467cfb6ffd3e9dd2d5a70"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>   
  +    [New 3DS 9.2.0 - JPN - ctrtransfer](torrents/9.2.0-20J_ctrtransfer_n3ds.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:b22d67fd02b3b0e30ac991e451db0f2d32e7beca"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>     
  +    [New 3DS 9.2.0 - USA - ctrtransfer](torrents/9.2.0-20U_ctrtransfer_n3ds.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:985d47442dc470d1b9f908256bed041c63885f60"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>    
~
  +    [Old 3DS or 2DS 9.2.0 - EUR - ctrtransfer](torrents/9.2.0-20E_ctrtransfer_o3ds.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:8d6142313971b08f92257e7fb1c1d5689e34ed78"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>     
  +    [Old 3DS or 2DS 9.2.0 - JPN - ctrtransfer](torrents/9.2.0-20J_ctrtransfer_o3ds.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:24ad2b85e67013ef1f91178dca7ad2e40663b9b2"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>     
  +    [Old 3DS or 2DS 9.2.0 - USA - ctrtransfer](torrents/9.2.0-20U_ctrtransfer_o3ds.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:1dc79a2a0babb45497961888f369423a93135e2b"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>

#### Instructions

**Some consoles have a `SecureInfo_B` instead of `SecureInfo_A`; this is fine and you should use `SecureInfo_B` for the relevant steps.**    

##### Section I - Prep work

1. Copy `GodMode9.bin` from the GodMode9 zip to the `/luma/payloads` folder on your SD card and rename `GodMode9.bin` in `/luma/payloads` to `up_GodMode9.bin`
2. Copy `Decrypt9WIP.bin` to the `/luma/payloads/` folder on your SD card and rename `Decrypt9WIP.bin` to `x_Decrypt9WIP.bin`
3. Copy the 9.2.0 ctrtransfer image `.bin` and `.bin.sha` from the ctrtransfer zip to the `/files9/` folder on your SD card
4. Reinsert your SD card into your 3DS

##### Section II - Backup tickets

5. Open Decrypt9 from arm9loaderhax by holding (X) during boot
6. Go to "Ticket/Titlekey Options", then select "Ticket Dump (SysNAND)"
7. Press (Select) to eject your SD card, then put it in your computer
8. Delete all `.tik` files in the `/files9/` folder that **do not** start with "00-"
9. Leave all the `.tik` files that do start with "00-" in the folder
10. Reinsert your SD card into your 3DS, then press (B)

##### Section III - ctrtransfer

5. Open Decrypt9 from arm9loaderhax by holding (X) during boot
6. Go to "SysNAND Options", then "CTRNAND Transfer", then "Auto CTRNAND Transfer"
7. Select the 9.2.0 ctrtransfer image when prompted by pressing (A)
8. **Backup SysNAND to `NANDmin.bin` when prompted by pressing (A)**
9. Allow the transfer process to proceed automatically, this may take some time
10. Once the transfer is complete, press Select to eject your SD card
11. Put your SD card in your computer, then copy `NANDmin.bin` and `NANDmin.bin.sha` from the `/files9/` folder on your SD card to a safe location; make backups in multiple locations; this backup will save you from a brick if anything goes wrong in the future **(Your backup should match one of the sizes on [this](nand-size) page; if it does not, you should delete it and make a new one!)**
12. Delete the 9.2.0 ctrtransfer image `.bin` and `.bin.sha` from the `/files9/` folder on your SD card after copying it
13. Reinsert your SD card into your 3DS

##### Section IV - Editing SecureInfo

1. Press (Start) then hold (Up) to reboot into arm9loaderhax GodMode9     
2. Navigate to `SYSNAND CTRNAND` -> `rw` -> `sys`
3. Press (Y) on `SecureInfo_A` to copy it
4. Press (Y) to paste a copy of `SecureInfo_A`
5. Select "Copy path(s)"
6. Press (A) to unlock SysNAND writing, then input the key combo given
7. Select "Choose new name"
8. Use the D-Pad to rename the file to `SecureInfo_C`, pressing (A) when you're done (overwrite any existing `SecureInfo_C`)
9. Scroll down to the `SecureInfo_C` you just pasted
10. Press (A) on `SecureInfo_C` then select "Show in Hexeditor"
11. Press (A) to continue
12. Press (A) to enter edit mode
13. Go to the beginning of line 00000100 and press (A) on it
14. Hold (A) while pressing (Up) or (Down) on the D-Pad to edit the number
15. Change the first number pair on line 00000100 to the following pair that corresponds to *the region you want to change to*:
    - "00" : JPN
    - "01" : USA
    - "02" : EUR
16. Press (B) to exit edit mode, then save changes, then press (B) again to return to the directory
17. You should see both a `SecureInfo_A` and `SecureInfo_C` if everything was done properly. (`SecureInfo_C` is used in place of `SecureInfo_A` when using Luma3DS if it detects the file on boot)
18. Press Start to reboot

##### Section V - Reinstalling Tickets

1. Open FBI
2. Select "SD"
3. Select "files9"
4. Select "\<current directory>"
5. Select "Install and delete all tickets"
6. Wait. The system may appear to freeze, just give it time.
7. Press (A) to confirm
8. Press (B) to decline installing tickets from CDN.
9. Exit with the home button

##### Section VI - Region settings

1. Open the System Settings
2. Go to "Other Settings", "Profile", then "Region Settings"
3. Select a country from the region you switched to
4. If prompted, you do not need to set a state
5. Update your region changed CFW SysNAND to the latest version
