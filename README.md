# OpenWRT-TP-Link-TL-WR902AC-V4
OpenWrt firmware for TP-Link TL-WR902AC-V4 travel router. 

As of November 2023, OpenWrt does not officially support the V4 for TP-Link TL-WR902AC. Although the v3 firmware would work it disables the 5Ghz radio amongst other issues. The firmware I have compiled works with v4 and all features seem to be working correctly however I have not throughly tested it and provide no warranty on anything in this repository. It is your responsibly to understand the process and risks of flashing your router using a third party firmware. That said, the compiled firmware has the following packages. 
* kmod-mt7615e - For the 5Ghz Chip
* kmod-mt7663-firmware-ap - For the 5Ghz Chip
* kmod-usb2 
* kmod-usb-ohci
* kmod-usb-ledtrig-usbport
* luci - GUI for OpenWrt
* travelmate - A Wlan connection manager for travel router. Refer to https://openwrt.org/packages/pkgdata/travelmate for details
* luci-app-travelmate 
* luci-ssl- For SSL connection to the router management GUI. 

Flashing Process:

Please refer to Openwrts instructions for v3 here (https://openwrt.org/toh/tp-link/tl-wr902ac_v3). They remain the same for v4. 

Be sure to verify the sha256 checksum for the .bin file with the downloaded sha256sums file. This is extremely important not since an improperly downloaded or corrupted firmware file will brick your router. For Linux use “sha256sum -a <filepath>”, for MacOS use command “shasum -a 256 <filepath>” in terminal. For Windows use “certutil -hashfile <path> SHA256” 

To revert back to the original firmware, you need a firmware file without the bootloader. TP-Link does not provide this file on their website. You could download the latest firmware from TP-Link's website and remove the first 512 bytes from the default firmware file. Alternatively you could download the TL-WR902AC(US)_V4_230504.bin from this repository and flash it since I have already removed the bootloader from the same.  
