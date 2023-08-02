dracut-exfatloop: Mount image on exFAT partition
==============================================

# Nothing here yet... Work in progress...
This work is inspired by [rgcjonas/dracut-ntfsloop](https://github.com/rgcjonas/dracut-ntfsloop).

This dracut module allows you to use a root system located inside
a disk image on an exFAT partition.

## Requirements

* dracut (tested with Asahi-Gentoo Linux)
* exfat, losetup
* exfat and loop kernel modules available

## Installation

## My Use Case

In my case the disk image contains a luks encrypted btrfs partition.
I'm putting my disk image on an [exFAT](https://wiki.gentoo.org/wiki/ExFAT) partition because Apple Mac and Linux both have good exFAT support.

From MacOS the exfat partition was create and is mounted.
From Docker on MacOS the disk image was created and formatted with btrfs
Therefore using Docker on Mac I can access the files from my Asahi Gentoo Linux system.
But I can also go further on the Mac, using [SSHFS](https://osxfuse.github.io/) from the Mac to mount the BTRFS from the docker container - now my Asahi Gentoo Linux system files are directly accessible from Finder on my MacOS install.

## Performance

I've not benchmarked anything...
I'm assuming the impact of having my btrfs partition on a loopback from ExFAT will be negligible for Asahi Gentoo Linux.

From the MacOS side there is a reasonable amount of overhead here, the docker container, OSXFuse, SSHFS.
But performance from here is less important to me than access itself.
