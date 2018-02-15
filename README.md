# Mybooklive debrick script

The purpose of the script is to reinstall the operating system (debrick) on a hard drive that has been extracted from the housing of a WD MyBook Live, originally posted [here](http://tandp.subankulov.com/archives/462).

The script will find out what disk to use, it will not touch the partition tables and therefore preserves data (if it's necessary). It will look what the newest version of the firmware is via internet and then search for it in current folder or subfolders. if none is found it will download one.

## Prerequisites  
* Debian or Ubuntu distro (including LiveCD),
* `rootfs.img` file (2GB) extracted from [here](http://download.wdc.com/nas/apnc-010507-20110714.deb) if you want to work offline.

## Usage
```
sudo ./debricker.sh <options>
```
possible options are:
* `/dev/sd?` - path to the disk from My Book Live. if not given, the script will figure it out on its own.
* `/*/*.img` - path to the firmware that will be written to the disk, if not given, the script will search for and then download it.
* `destroy` - script will rewrite the partition table of disk, this will not preserve data, must match `/dev/sd?`.

Example:
```
sudo ./debricker.sh /dev/sda /firmwares/rootfs.img destroy
```
