# ARC_PLOT
First CPU + GPU plotter focus on Consumer hardware, with various topology.

vision:
Plotting should be green use less engery, cheap or spare haredware.
ARC_PLOT is unique as it's the first plotter which support CPU + GPU plotting.

-----------------------------------------------------------------------------------------------------------
1. Plot architecture.

Arc_plot can run in differrent topology.

a.) standalone 32G ram + 256 SSD

b.) standalone with 128G ram + 128G ssd

c.) NRD 128G x2 pc + standalone 32G ram.

d.) combine with GPU in standalone plotter.

please check wiki for details.

-----------------------------------------------------------------------------------------------------------
2. Release notes.

v0.6.1 Add "-G" mode, which using GPU to plotting phase1.

next release feature: add GPU algo for compressing phase.

GPU plotting requirements:

hardware:

cpu: *4 core x86 cpu with pci-e 3.0 x16 bus*

ram: *128G ram*

gpu: *nvidia cuda compatibility > 7.5 GPU ( 20 or 30 series) with 8G+ vram.*

ssd: *MLC or TLC with good continuous sequence R/S speed. ( found some QLC ssd will have fwrite() error if speed lag thd GPU too much.) and ramdisk for tmp1 folder prefered if you have more ram or config at least 32G swap file*

Software:

ubuntu 22.04.


-----------------------------------------------------------------------------------------------------------
3. Benchmark.

you can download the arc_plot and try it with GPU for phase1. it's still alpha, but your feedback is very valuable.
please submit your benchmark by a github ticket 

arc_plot 0.6.1 for ubuntu 22.04 download link:

[https://github.com/smartbitcoin/arc_plot/raw/main/arc_plot.0.6.ubuntu22.04.tar.bz2](https://github.com/smartbitcoin/arc_plot/raw/main/arc_plot.0.6.1.ubuntu22.04.tar.bz2)

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
