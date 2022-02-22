# xlnx-firmware
This is the set of firmware files that make up the xlnx-firmware debian package for the ZCU102/4/6 development boards. The debian pacakge is managed and distributed by Canonical. 

Each board-specific bootXXXX.bin in the certifed Ubuntu ZCU10x image from Canonical (ex: boot1061.bin) contains a set of boot artifacts from a Xilinx reference design, plus the Canonical-generated u-boot image. The default reference design platforms for the three boards are: 

# Ubuntu 22.04 LTS Release:
- ZCU102: [PetaLinux 2022.1 BSP]()
- ZCU104: [PetaLinux 2022.1 BSP]()
- ZCU106: [PetaLinux 2022.1 BSP]()
- ZCU111: [PetaLinux 2022.1 BSP]()

*_NOTE_: The 22.04 firmware images do NOT contain programmable logic (PL) resources*

# Ubuntu 20.04 LTS Release:
- ZCU102: [Vitis AI v1.3 MPSoC DPU TRD](https://github.com/Xilinx/Vitis-AI/tree/v1.3.2/dsa/DPU-TRD/prj/Vitis)
- ZCU106: [2020.2 VCU HDMI ROI TRD](https://xilinx-wiki.atlassian.net/wiki/spaces/A/pages/1186693157/Zynq+UltraScale+MPSoC+ZCU106+VCU+HDMI+ROI+TRD+2020.2)
- ZCU104:  [2020.2 VCU HDMI ROI TRD](https://xilinx-wiki.atlassian.net/wiki/spaces/A/pages/1268973650/Zynq+UltraScale+MPSoC+ZCU104+VCU+HDMI+ROI+2020.2)



---
Copyright (C) 2021 - 2022 Advanced Micro Devices, Inc / Xilinx, Inc All rights reserved.
