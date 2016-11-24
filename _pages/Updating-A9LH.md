---
title: "更新A9LH"
permalink: /updating-a9lh.html
---

### Last Update: 3 Nov 2016

The actual installation of arm9loaderhax itself consists of payload files installed into the NFIRM partitions on your device's NAND chip, which is soldered to the motherboard itself. These payloads are updated rarely and only really serve the purpose of launching `arm9loaderhax.bin` from the SD Card, which is, in our case, Luma3DS.
{: .notice}

If you do not know what version of arm9loaderhax you are running, just install the latest version with these steps. Installing the latest version while already on the latest version will have no effect.
{: .notice--info}

If you have a PIN set on Luma, you must temporarily turn it off to do these steps. You can re-enable the PIN after the update.
{: .notice--info}

If you are using a payload that does not init the screen on its own (such as Bootanim9), you will need to rename it to `arm9loaderhax_si.bin` instead of `arm9loaderhax.bin`
{: .notice--info}

These steps will also update your various payloads and the AES key database.
{: .notice--success}

#### What you need

* [`aeskeydb.bin`](torrents/aeskeydb.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:18b3a17f78e2376e05feaa150749d9fd689b25dc"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
* [`data_input_v3.zip`](torrents/data_input_v3.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:a1195c9f7ab650fa7c7bf020b51fc19ea8d9440c"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
* The latest release of [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest)
* The latest release of [arm9loaderhax](https://github.com/AuroraWright/arm9loaderhax/releases/latest)
* The latest release of [SafeA9LHInstaller](https://github.com/AuroraWright/SafeA9LHInstaller/releases/latest)
* The latest release of [Hourglass9](https://github.com/d0k3/Hourglass9/releases/latest)

#### Instructions

**For all of these instructions, OVERWRITE any existing files on your SD card.**

##### Section I - Prep work

1. Delete any existing `aeskeydb.bin` from the root of your SD card
4. Delete the `a9lh` folder from the root of your SD card if it exists
2. Copy `aeskeydb.bin` to the `/files9/` folder on your SD card
3. Copy `Hourglass9.bin` from the Hourglass9 zip to the `/luma/payloads/` folder on your SD card and rename `Hourglass9.bin` to `start_Hourglass9.bin`
5. Copy `arm9loaderhax.bin` from the SafeA9LHInstaller zip to the `/luma/payloads` folder on your SD card
6. Rename `arm9loaderhax.bin` in `/luma/payloads` to `down_safea9lhinstaller.bin`
7. Copy the `a9lh` folder from `data_input_v3.zip` to the root of your SD Card
7. Copy _the contents of_ the arm9loaderhax zip to `a9lh` folder on your SD card
8. Copy `arm9loaderhax.bin` from the Luma3DS zip to the root of your SD card, overwrite existing files
9. Reinsert your SD card into your 3DS

##### Section II - Payload update

10. Boot the device while holding D-Pad down
11. Press (Select) to update arm9loaderhax
12. Power off the device and put your SD card back in your computer
13. Delete the `a9lh` folder from the root of your SD card
14. Delete `down_safea9lhinstaller.bin` from `/luma/payloads`

##### Section III - Configuring Luma3DS

15. Reinsert your SD card into your 3DS and boot holding (Select)
16. Use the (A) button and the D-Pad to turn on the following:    
  + **"Autoboot SysNAND"**
  + **"Use SysNAND FIRM if booting with R (A9LH)"**
  + **"Show NAND or user string in System Settings"**
3. If you are using a **New 3DS**, you should *also* enable the following:
  + **"New 3DS CPU" to "Clock+L2(x)"**
    + This will increase the framerate of many games, but may cause instability in others
    + If some games do not work properly, disable this option and try again
4. Press Start to save and reboot

##### Section IV - CTRNAND Luma3DS

16. Open FBI
17. Select "SD"
18. Navigate to `arm9loaderhax.bin`, then press (A) on it and select the "Copy" option
9. Return to the FBI main menu with (B)
10. Select "CTR NAND"
11. Select "\<current directory>"
12. Select the "Paste" option, then press (A) to confirm
8. Exit with the home button
9. Power off your 3DS and remove the SD card
10. Boot with the SD card removed while holding (Select)
  + Booting the device at least once with the SD card removed will allow you to configure the CTRNAND based luma installation
16. Use the (A) button and the D-Pad to turn on the following:    
  + **"Show NAND or user string in System Settings"**
3. If you are using a **New 3DS**, you should *also* enable the following:
  + **"New 3DS CPU" to "Clock+L2(x)"**
    + This will increase the framerate of many games, but may cause instability in others
    + If some games do not work properly, disable this option and try again
14. Reinsert your SD card, then press Start to save and reboot!
