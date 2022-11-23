# ARC_PLOT
First GPU plotter focus on Consumer hardware, with Network Ram Disk setup.

vision:
Plotting should be green use less engery, cheap or spare haredware.
ARC_PLOT is unique as it's the first plotter which take GPU and NetworkRamDisk( NRD ) to plotting community.

-----------------------------------------------------------------------------------------------------------
1. Plot architecture.

As a full ram based green plotter, arc_plot can be deployed as a cluster topology. there are two major component, the high-end plotting PC and the low end network ram disk (NRD) pc.
For high end plotting PC, more core and high freq ram is prefered. For NRD pc, 2 or 4 core , cheap ddr3 or 4 ram 128G to 256G preferred.

![Screenshot from 2022-11-22 23-39-14](https://user-images.githubusercontent.com/5984485/203470336-9b3a14c5-f970-41c8-a359-e5fdb3e5e9eb.png)

Plotting pc connecting to NRD with thunderbolt 4 or 10G nic, running ethernet network. Plotting PC mount remote ram disk as a network blocking devices. and multiple those devices was build a raid0.


-----------------------------------------------------------------------------------------------------------
2. Plot setup.

a) prepare NRD pc.
install ubuntu 22.04 minimum server installation.
install nbd package.
```
sudo apt install nbd-server
```
create virtual ram disk and mount into /mnt
```
sudo mount -t tmpfs -o size=126G tmpfs /mnt
cd /mnt/
fallocate -l 126G ram 
chmod 777 ram
```
start nbd server, export /mnt/ram as remote block device on port 11111
```
sudo nbd-server 11111 /mnt/ram
```

b) prepare plotting pc.
install ubuntu 22.04 minimum server installation.
install nbd package.
```
sudo apt install nbd-client
sudo modprobe nbd
```
then you can see virtual blocking device in /dev/nbd0-15
mount remote ram disk into plotting pc
```
sudo nbd-client -b 4096 -C 2 NRD_PC_1_IP 11111 /dev/nbd0
sudo nbd-client -b 4096 -C 2 NRD_PC_2_IP 11111 /dev/nbd1
```
create a ram disk raid0 by btrfs
```
sudo mkfs.btrfs -n 64k -m raid0 -d raid0 /dev/nbd0 /dev/nbd1 -f
```
mount nbd raid into your plotting path.
```
sudo mount /dev/nbd0 /your_plotting_ramdisk_path
```
add permission to this ram disk
```
sudo chown -R your_id /your_plotting_ramdisk_path
```

all done.

then you can start happy plotting lol

-----------------------------------------------------------------------------------------------------------
3. Benchmark.

you can download the arc_plot and try it with this network ram disk prototype. it's still alpha, but your feedback is very valuable.
please submit your benchmark by a github ticket 

arc_plot alpha0 for ubuntu 22.04 download link:

https://github.com/smartbitcoin/arc_plot/releases/download/alpha0/arc_plot.alpha.ubuntu22.04.tar.bz2


4. arc_plot still under constrution, but there was some POC video with more details.

https://www.youtube.com/watch?v=CfmZbIM17ZQ&t=87s


-----------------------------------------------------------------------------------------------------------

Special thanks to MadMax and Bladebit as arc_plot learned lots of good design from them and here show highly respect for these complicated project and pioneer's hardwork.

ARC_PLOT is freeware and if you like this idea and love the arc_plot freeware, please don't forget donoate some XCH to support this project.
