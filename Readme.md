ZynqMP-FPGA-XRT-Example-1-Ultra96
=======================================================================

This Repository provides example for ZynqMP-FPGA-XRT.

ZynqMP-FPGA-XRT is XRT(Xilinx RunTime) Debian Package for ZynqMP-FPGA-Linux.

## Requirement

  * Board: One of following
    - Ultra96
    - Ultra96-V2
  * OS: One of following
    - https://github.com/ikwzm/ZynqMP-FPGA-Linux
    - https://github.com/ikwzm/ZynqMP-FPGA-Ubuntu18.04-Ultra96
  * XRT(Xilinx RunTime) 
    - https://github.com/ikwzm/ZynqMP-FPGA-XRT

## Usage

### Setup Xilinx Runtime Environment

```console
shell$ source /opt/xilinx/xrt/setup.sh
XILINX_XRT      : /opt/xilinx/xrt
PATH            : /opt/xilinx/xrt/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games
LD_LIBRARY_PATH : /opt/xilinx/xrt/lib:
PYTHONPATH     : /opt/xilinx/xrt/python:
```

### Preparation of zocl

```console
shell$ sudo ./dtbocfg.rb --install zocl --dts zocl.dts
shell$ dmesg | tail -12
[  922.858337] fpga_manager fpga0: writing streaming_lap_filter5.bin to Xilinx ZynqMP FPGA Manager
[  923.009621] [drm] Probing for xlnx,zocl
[  923.009732] [drm] FPGA programming device pcap founded.
[  923.009737] [drm] PR Isolation addr 0x0
[  923.010163] [drm] Initialized zocl 2018.2.1 20180313 for a0000000.zyxclmm_drm on minor 1
[  923.013226] fclkcfg amba_pl@0:fclk0: driver installed.
[  923.013241] fclkcfg amba_pl@0:fclk0: device name    : amba_pl@0:fclk0
[  923.013245] fclkcfg amba_pl@0:fclk0: clock  name    : pl0_ref
[  923.013252] fclkcfg amba_pl@0:fclk0: clock  rate    : 99999999
[  923.013275] fclkcfg amba_pl@0:fclk0: clock  enabled : 1
[  923.013279] fclkcfg amba_pl@0:fclk0: remove rate    : 1000000
[  923.013284] fclkcfg amba_pl@0:fclk0: remove enable  : 0
```

### Run streaming_lap_filter5.exe

```console
shell$ ./streaming_lap_filter5.exe streaming_lap_filter5.xclbin
Using FPGA binary file specfied through the command line: streaming_lap_filter5.xclbin
Found Platform
Platform Name: Xilinx
Loading: 'streaming_lap_filter5.xclbin'
total time = 0.001304 sec
Success HW and SW results match
```

