---
title: "NTR and Cubic Ninja"
permalink: /ntr-and-cubic-ninja.html
---

**NTR Cubic Ninja will work for JPN New 3DS ONLY!**
{: .notice--warning}

#### What you need

* [JPN Cubic Ninja](https://www.amazon.com/dp/B004QL7M0A)
* The Homebrew [Starter Kit](http://smealum.github.io/ninjhax2/starter.zip)
* The latest release of [Decrypt9WIP9](https://github.com/d0k3/Decrypt9WIP/releases/latest)
* [`3ds-private-update-server.zip`](torrents/3ds-private-update-server.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:8623e580752f22940d96630ef723ce30a707b22e"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
* [WAMPSERVER (PHP 5.5) 2.5](http://www.wampserver.com/en/#download-wrapper)
* [`node.exe`](http://nodejs.org/dist/latest/win-x86/node.exe)
* [`update.php`](torrents/update.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:cd7e59ea9744115913b561dbde15f8d68e713507"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
* The v3.2 release of [NTR CFW](https://github.com/44670/BootNTR/releases/tag/3.2)
* The latest release of [NTR Debugger](torrents/NTR%20Debugger.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:66274cee542bef7745792714673bf2be4d606496"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>
* The 9.2.0 downgrade pack zip file for your device and region:  
 +    [New 3DS 9.2.0 - JPN](torrents/9.2.0-20J(Full)_n3DS.torrent) - <code class="highlighterrouge"><a href="magnet:?xt=urn:btih:c8630ed31b53637b9023bd4dc1ce38362bb8ecd9"><i class="fa fa-magnet" aria-hidden="true"></i></a></code>     

#### Instructions

##### Section I - Prep Work

1. Install WAMP to the default directory
2. Copy the contents of `3ds-private-update-server.zip` to `C:\wamp\www\` (overwrite existing files)
3. Copy `update.php` to `C:\wamp\www\` (overwrite existing files)
4. Copy the `updates` folder from the 9.2.0 downgrade zip to `C:\wamp\www\`
5. Move `node.exe` to `C:\wamp\www\updates`
6. Move `C:\wamp\www\CdnCiaUnpack.js` to `C:\wamp\www\updates`
7. In the `C:\wamp\www\updates` directory, drag `CdnCiaUnpack.js` onto `node.exe` to create `GetSystemUpdate.partial.xml`
8. Move `node.exe` and `CdnCiaUnpack.js` back to `C:\wamp\www\`
9. Copy `GetSystemUpdate.partial.xml` to `C:\wamp\www\` (so that a copy of it exists in both `C:\wamp\www\updates` and `C:\wamp\www\`)
9. Click the WAMP icon in your system tray, then click "Put Online"
10. Use the command "ipconfig" in CMD to get your computer's IPv4 Address, you will need it soon
11. Copy `ntr.bin` to the root of your SD card
12. Create a folder named `files9` on the root of your SD card if it does not already exist
1. Copy _the contents of_ the `starter.zip` to the root of your SD card, then put the SD card back into your 3DS
2. Copy the `Decrypt9WIP` folder from the Decrypt9WIP zip to `/3ds/` on your SD card

##### Section II - Updating

1. Boot your 3DS into recovery mode by holding L+R+A+UP while powering on
2. Decline the update and reboot
3. Open Cubic Ninja (if it already has NinjHax installed, hold L+R+X+Y to reset it)
4. Select "Create", then "QR Code", then "Scan QR Code"
5. Scan the QR code in the NTR CFW zip for your region
6. On the home menu, press (Y) and (X) at the same time to open NTR's menu
7. Enable the debugger and close the menu
8. Use your router's web page to get your 3DS's IP address (google it if you don't know how, all routers are different)
9. Run NTR Debugger on your computer
10. Enter the following commands (replace 192.168.1.100 with your 3DS's IP address and 192.168.1.200 with your computer's IP address)    
    + `connect("192.168.1.100", 8000)`
    + `write(0x15E424, tuple(map(ord, "http://192.168.1.200/update.php\0")), pid=0x25)`
    + `write(0x15E0EC, tuple(map(ord, "http://192.168.1.200/update.php\0")), pid=0x25)`
    + `write(0x15E463, tuple(map(ord, "http://192.168.1.200/update.php\0")), pid=0x25)`
11. Update your 3DS by going to System Settings, then "Other Settings", then going all the way to the right and using "System Update"

___

Continue to [Installing arm9loaderhax](installing-arm9loaderhax).
