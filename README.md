**Wiscore Alexa Support USB And SD**

Here you can use the firmware in wiscore directly, or build by yourself
[WisCore Quick Start](https://github.com/RAKWireless/WisCore)

Enable usb and sdcard:
1. download config files
2. Replace the old config files

          cp .config products/wisCore/opwrt-wisavs-topv002-1-20170519.config
     
          cp config-3.18 products/wisCore/target/linux/ramips/mt7628/config-3.18
     
          cp MT7628.dts products/wisCore/target/linux/ramips/dts/

3. re-build workspace
     [build](https://github.com/RAKWireless/WisCore/wiki/WisCore)
     or use command directly:
     
     ./build/envsetup.sh wisCore hgw
     
     make

4. Finally burn the image and use it

*sdcard and LAN port are in conflict, you can change sd driver to use LAN port*

     vi build_dir/target-mipsel_24kec+dsp_uClibc-0.9.33.2/linux-ramips_mt7628/linux-3.18.45/drivers/mmc/host/mtk-mmc/sd.c +3021

     change "reg |= 0x1e << 16"  to "reg |= 0x18 << 16"
