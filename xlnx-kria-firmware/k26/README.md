Introduction and Overview
-------------------------
This directory contains details on using the device tree source (.dts) files for Kria SOMs.  The Kria SOMs make extensive use of device tree and device tree overlays in order to enable maximum flexibility.  The Kria software architecture begins with a minimal device tree file in the QSPI firmware and loads progressively more complete representations of the target system programmatically at runtime.  For full detailsm, please see the Kria wiki at https://xilinx-wiki.atlassian.net/wiki/spaces/A/pages/1641152513/Kria+K26+SOM

The Kria Starter Kit QSPI image comes pre-programmed from the Xilinx factory and includes the following components and should not be modified:

* The Xilinx First Stage Boot Loader (FSBL)
* The initial U-Boot device tree blob (.dtb)
* The U-Boot binary (.elf)

Kria K26 SOM Device Tree Files - Xilinx Vivado 2022.1 / Ubuntu 22.04 LTS Release
-----------------------------------------------------
For the Vivado 2022.1 release, the Kria DTS files are now found in the public Linux source tree.  They were committed here: https://github.com/Xilinx/linux-xlnx/commit/70604467dc949d3b77eabaa1288365cb25b2ec23

|   File Name                            | Description                       |
|   :-------------------------------     | :------------------------------   |
|   `zynqmp-sck-kr-g-revA.dts`           | Revision A KR Carrier Card DTS    |
|   `zynqmp-sck-kr-g-revB.dts`           | Revision B KR Carrier Card DTS    |
|   `zynqmp-sck-kv-g-revA.dts`           | Revision A/Z KV Carrier Card DTS  |
|   `zynqmp-sck-kv-g-revB.dts`           | Revision B/1 KV Carrier Card DTS  |

Some device tree files - such as the Display Port DTS noted in the table above - are loaded after Linux has started and are used to support specific reference or demo applications.

The Revision A and Revision Z boards use the same DTS file.  The Revision B and Revision 1 boards use the same DTS file.

Building the Kria K26 SOM Device Tree Files
--------------------------------------------
The device tree files can be build using the standard open source device tree compiler (dtc) tool located at https://git.kernel.org/pub/scm/utils/dtc/dtc.git

For example:
```
dtc -I dts -O dtb -o zynqmp-sck-kv-g-rev1.dtbo zynqmp-sck-kv-g-rev1.dts
dtc -I dts -O dtb -o zynqmp-sck-kv-g-revZ.dtbo zynqmp-sck-kv-g-revZ.dts
dtc -I dts -O dtb -o zynqmp-sck-kv-g-revB.dtbo zynqmp-sck-kv-g-revB.dts
```

Alternatively, the device tree files can be built using the Linux kernel `make` infrastructure
```
$ make ARCH=arm64 xilinx_zynqmp_defconfig
$ make ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu- dtbs
```

---
Copyright (C) 2021 - 2022 Advanced Micro Devices, Inc / Xilinx, Inc All rights reserved.
