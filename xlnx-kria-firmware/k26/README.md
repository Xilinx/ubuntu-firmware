Introduction and Overview
-------------------------
This directory contains device tree source (.dts) files the Kria SOMs.  The Kria SOMs make extensive use of device tree and device tree overlays in order to enable maximum flexibility.  The Kria K26 software architecture starts with a minimal device tree during initial boot in the on-board QSPI and selectively adds additional device tree overlays as boot progresses.  The Kria K26 Starter Kit QSPI image comes pre-programmed from the Xilinx factory and includes the following components and should not be modified:

* The Xilinx First Stage Boot Loader (FSBL)
* The initial U-Boot device tree blog (.dtb)
* The U-Boot binary (.elf)

Kria K26 SOM Device Tree Files
-----------------------------------------------------

During the hand-off to Linux, the base device tree used during boot is extended depending on the SOM and carrier card combination detected at runtime.  All Kria SOMs start Linux boot with a file called `system.dts`.  As boot progresses, additional device support is added based on the detected carrier card.

|   File Name                          | Description                       |
|   :-------------------------------   | :------------------------------   |
|   `system.dts`                         | Base Linux DTS                    |
|   `zynqmp-sck-kv-g-revZ.dts`           | Revision Z Carrier Card DTS       |
|   `zynqmp-sck-kv-g-rev1.dts`           | Revision 1.0 Carrier Card DTS     |
|   `zynqmp-sck-kv-g-dp.dts`             | Display Port DTS                  |
|   `zynqmp-sck-kv-g-revB.dts`           | Revision B Carrier Card DTS       |

Some device tree files - such as the Display Port DTS noted in the table above - are loaded after Linux has started and are used to support specific reference or demo applications.

Getting the Kria K26 SOM Device Tree Files
---------------------------------------
```
git clone https://github.com/Xilinx/ubuntu-firmware.git
```

Building the Kria K26 SOM Device Tree Files
--------------------------------------------
The device tree files can be build using the standard open source device tree compiler (dtc) tool located at https://git.kernel.org/pub/scm/utils/dtc/dtc.git
```
cd ubuntu-firmware/xlnx-kria-firmware/k26
dtc -I dts -O dtb -o system.dtb system.dts -p 0x1000
dtc -I dts -O dtb -o zynqmp-sck-kv-g-rev1.dtbo zynqmp-sck-kv-g-rev1.dts
dtc -I dts -O dtb -o zynqmp-sck-kv-g-revZ.dtbo zynqmp-sck-kv-g-revZ.dts
dtc -I dts -O dtb -o zynqmp-sck-kv-g-dp.dtbo zynqmp-sck-kv-g-dp.dts
dtc -I dts -O dtb -o zynqmp-sck-kv-g-revB.dtbo zynqmp-sck-kv-g-revB.dts
```

---
(c) Copyright 2021 Xilinx, Inc. All rights reserved.
