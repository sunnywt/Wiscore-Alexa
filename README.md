**Wiscore Alexa Support USB And SD**

Here you can use the firmware in wiscore directly, or build by yourself
download WisCore-SDK: https://github.com/RAKWireless/WisCore-SDK

Enable usb and sdcard:
1. download config files
2. Replace the old config files
     cp .config products/wisCore/opwrt-wisavs-topv002-1-20170519.config
     cp config-3.18 products/wisCore/target/linux/ramips/mt7628/config-3.18
     cp MT7628.dts products/wisCore/target/linux/ramips/dts/

3. re-build workspace
     refer to github: https://github.com/RAKWireless/WisCore/wiki/WisCore

     or use command directly:
     ./build/envsetup.sh wisCore hgw
     make

4. Finally burn the image and use it
