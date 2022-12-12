# ARC_PLOT
CPU + GPU plotter.

MileStone in v0.6.2 : first time a PC plotter can be less than 10 mins  with gpu acceleration.!
-----------------------------------------------------------------------------------------------------------
1. Plotter setup:

a.) standalone 32G ram + 256 SSD

b.) standalone 128G ram + 128G ssd

c.) local 32G ram + NRD disk 128G x2 pc 

d.) 128G cpu + 8G vram GPU.

How to run:
get help:
./arc_plot --help

run:
cpu: 32G + SSD
./arc_plot -r cpu_core_num -n num_of_plots -u 256 -v 256 -t your_ssd_path -d your_distination_path -c your_contract -f your_farm_key

cpu:110G
./arc_plot -R -r cpu_core_num -n num_of_plots -u 256 -v 256 -t your_ssd_path -d your_distination_path -c your_contract -f your_farm_key

cpu+gpu: 110G
./arc_plot -G -r cpu_core_num -n num_of_plots -u 256 -v 256 -t your_ssd_path -d your_distination_path -c your_contract -f your_farm_key

-----------------------------------------------------------------------------------------------------------
2. Release notes.

v0.6.2 partial gpu compressing phase implemented. compressing phase time reduce 50%.

next release feature: add GPU algo for compressing phase.

more details please check: 
https://github.com/smartbitcoin/arc_plot/blob/main/release_notes

GPU plotting requirements:

hardware:

cpu: *4 core x86 cpu with pci-e 3.0 x16 bus*

ram: *128G ram*

gpu: *nvidia cuda compatibility > 7.5 GPU ( 20 or 30 series) with 8G+ vram.*

ssd: *MLC or TLC with good continuous sequence R/S speed. QLC should use raid0. ( found some SSD have fwrite() error if speed lag thd GPU too much.) 

Software:

ubuntu 22.04.


-----------------------------------------------------------------------------------------------------------
3. Benchmark.

please submit your benchmark by a github ticket 

arc_plot 0.6.2 for ubuntu 22.04 download link:

[https://github.com/smartbitcoin/arc_plot/raw/main/arc_plot.0.6.2.1.ubuntu22.04.tar.bz2](https://github.com/smartbitcoin/arc_plot/raw/main/arc_plot.0.6.2.1.ubuntu22.04.tar.bz2)

windows user please check: ( not sure how wsl support gpu though.)

https://github.com/smartbitcoin/arc_plot/wiki/arc_plot-windows-wsl-guide.

a benchmark can be also found in wiki:

https://github.com/smartbitcoin/arc_plot/wiki

briefly compare speed of gpu vs cpu.  rtx 3090 = 2 x i9 13900kf for phase1.

4. arc_plot still under constrution, but there was some POC video with more details.

https://www.youtube.com/watch?v=CfmZbIM17ZQ&t=87s


-----------------------------------------------------------------------------------------------------------

Special thanks to MadMax and Bladebit as arc_plot learned lots of good design from them and here show highly respect for these complicated project and pioneer's hardwork.

ARC_PLOT is freeware and if you like this idea and love the arc_plot freeware, please don't forget donate some XCH to support this project.

xch12qge50ttf5c6lcx7at3295q92wndfapyuvr920j88zdnfqzc8ggqaja0dn
