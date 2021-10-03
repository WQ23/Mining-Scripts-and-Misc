A compilation of scripts and miscellaneous settings I found all over the internet, used to optimise GPU mining performance for (mainly) Ethereum


BTC: 3QJ4YG8HaSoErMs8yHKwUEGyEgtK5c2LT6

=================================================================================================================================

RX Vega 56 (Gigabyte / Samsung Memory / Stock cooler) ~54 MH/s stable

amdmemtweak --CL 20 --RC 38 --RP 12 --WR 13 --CWL 8 --FAW 12 --RAS 26 --REF 24000 --RFC 239 --RTP 6 --RRDL 5 --RRDS 3 --WTRL 9 --WTRS 4 --RCDRD 12 --RCDWR 12

Core: 1100
Core Voltage: 850
Memory Controller Voltage: 0
Memory Clock: 1020
Memory Voltage: 0
Fan: Typically 60%+, mine are kept above 75%

=================================================================================================================================

RTX 3080 MSI Gaming X/Z Trio without modding thermal pads and voiding warranty, while retaining RGB controls unlike flashing Suprim / Strix Bios ~101 MHs stable
-Bios flash to this: https://www.techpowerup.com/vgabios/231648/msi-rtx3080-10240-210311
-Extra info: https://www.nvidia.com/en-us/geforce/news/geforce-rtx-30-series-resizable-bar-support/

Fan: 100% (More economical replacing faulty fans vs getting a damaged core)

Varies greatly by card, but my settings are:
Memory Clock: +1315
Power Limit: 102%
Core Voltage: Untouched
Core Clock:Curve locked at 1140 / 700 on Afterburner

=================================================================================================================================

RX580 30+ MH/s stable

amdmemtweak --REF 30 (probably unnecessary)

Varies around these settings by model and memory type (Samsung / Hynix / Micron / Elpida)
Core Clock: 1150
Core Voltage: 850
Memory Clock: 2050
Fan: Typically ~50%, mine are kept above 60% in a closed rig

=================================================================================================================================


Installing generic wifi adapter driver on Linux (ls-usb 0bda-c811)
sudo apt update
sudo apt install build-essential git dkms
git clone https://github.com/brektrou/rtl8821CU.git
cd rtl8821CU
chmod +x dkms-install.sh
sudo ./dkms-install.sh

=================================================================================================================================

OverdriveNTool overclock.bat in startup folder to automatically apply overclocks:
OverdriveNTool.exe -r0 -p0"g0" -r1 -p1"g1" -r2 -p2"g2" -r3 -p3"g3" -r4 -p4"g4" -r5 -p5"g5" -r6 -p6"g6" -r7 -p7"g7"

=================================================================================================================================

TeamRedMiner launch scripts for Windows (B mode + compute mode toggle + coloured text + UAC):
launch.sh
teamredminer --algo ethash -o <pool address> -u <user> -p x --eth_dag_slowdown=9 --eth_no_ramp_up --enable_compute --force_colors --uac --eth_aggr_mode --eth_config=B --bus_reorder --api_listen=127.0.0.1:4028

launch.ps1 (when running multiple miners with clashes, easy solution is to run using Powershell)
Start-Process -NoNewWindow -FilePath "C:\x\teamredminer" -ArgumentList "-a ethash -o ......................"

=================================================================================================================================

Setup for Windows:
DDU
Registry tweaks
nvflash
amdmemorytweak
amdvbflash
Pixel Patcher
OverdriveNTool
GPU-Z
hwinfo

