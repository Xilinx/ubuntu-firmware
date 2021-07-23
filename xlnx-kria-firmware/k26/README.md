How To Get DTB/DTBO for SOM Starterkit

git clone https://github.com/Xilinx/ubuntu-firmware.git
cd ubuntu-firmware/xlnx-kria-firmware/k26

k26 directory has all the dts files mentioned below :

Base Linux DTS:                 system.dts
Revision Z Carrier Card DTS:    zynqmp-sck-kv-g-revZ.dts
Revision 1.0 Carrier Card DTS:  zynqmp-sck-kv-g-rev1.dts
Display Port DTS:               zynqmp-sck-kv-g-dp.dts


Please use the Linux DTC tool to build the DTB/DTBO files from DTS.
example :
dtc -I dts -O dtb -o system.dtb system.dts -p 0x1000
dtc -I dts -O dtb -o zynqmp-sck-kv-g-rev1.dtbo zynqmp-sck-kv-g-rev1.dts
dtc -I dts -O dtb -o zynqmp-sck-kv-g-revZ.dtbo zynqmp-sck-kv-g-revZ.dts
dtc -I dts -O dtb -o zynqmp-sck-kv-g-dp.dtbo zynqmp-sck-kv-g-dp.dts

Note: The K26 Starter Kit QSPI image comes pre-programmed from the Xilinx factory and includes
the U-Boot elf and U-Boot dtb. These components should be viewed as static and must support
the boot of both PetaLinux based Linux SD card images as well as Ubuntu SD card images.

---
(c) Copyright 2021 Xilinx, Inc. All rights reserved.
