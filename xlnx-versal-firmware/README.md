# xlnx-versal-firmware
This is the set of firmware files that make up the xlnx-versal-firmware debian package for the Versal development boards. The debian pacakge is managed and distributed by Canonical. 

Each board-specific bootXXXX.bin in the certifed Ubuntu Versal image from Canonical (ex: boot1901.bin) contains a set of boot artifacts from a Xilinx reference design, plus the Canonical-generated u-boot image. The default reference design platforms for the three boards are: 

# Ubuntu 24.04 LTS Release:
- VEK280: [Petalinux 2024.1 BSP](https://gitenterprise.xilinx.com/ubuntu-dev/ubuntu-firmware/tree/ubuntu-24.04-staging/xlnx-versal-firmware)

# Ubuntu 22.04 LTS Release:
- VCK190: [2022.1 VCK190 Base TRD - Single Sensor v1.4](https://github.com/Xilinx/vck190-base-trd/tree/xilinx-2022.1-v1.4)

---
Copyright (C) 2021 - 2022 Advanced Micro Devices, Inc / Xilinx, Inc All rights reserved.
