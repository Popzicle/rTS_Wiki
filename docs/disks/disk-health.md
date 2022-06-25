---
layout: default
title: Wiping Disks
nav_exclude: false
nav_order: 2
has_children: false
parent: Disks
search_exclude: false
last_modified_date: 2022-06-23
---

# Verifying Disk Health
## Definitions

S.M.A.R.T. - this is a monitoring system included in disk drives(HDDs and SSDs). Its primary function is to detect and report various indicators of drive reliability and health.

Sectors - these are sections of your hard drive that store data. Your hard drive has many many sectors.

## Important SMART Values

If you ever read a SMART report from any of the below tools it is useful understanding the common ones that you want to watch for.
Current Pending Sector Count

When a sector is detected as bad it will be counted and the disk will attempt to move it. This value can go up and down as the disk moves or recovers sectors.

[More info](https://harddrivegeek.com/current-pending-sector-count/)

## Reallocated Sectors Count

When detected as bad your disk will attempt to move a sector. If it is moved successfully this count will go up.

[More info](https://harddrivegeek.com/reallocated-sector-count/)

## Uncorrectable Sector Count

This count goes up when the disk is not able to recover and move a sector. This indicates lost data.

## Crystal Disk Info

Crystal disk is the simplest way to get a reading on SMART within Windows. Download the application then run it to view every disk in the machine.

If a disk shows up as Yellow 'Caution' or Red 'Bad' we recommend replacing it.

[Download](https://osdn.net/frs/redir.php?m=acc&f=crystaldiskinfo%2F74490%2FCrystalDiskInfo8_10_0.zip)

## Hard Disk Sentinel

[Download](https://www.hdsentinel.com/download.php)

## SEAGATE (SeaTools)

### Bootable
[Info](https://www.seagate.com/manuals/software/seatools-bootable/introduction/)

[Download](https://www.seagate.com/files/old-support-files/seatools/USBbootSetup-SeaToolsBootable.zip)

### Windows Application

[Info](https://www.seagate.com/files/www-content/support-content/downloads/seatools/_shared/downloads/pdf/SeaTools-for-windows-en-us.pdf)

[Download](https://www.seagate.com/files/old-support-files/seatools/USBbootSetup-SeaToolsBootable.zip)

## SmartmonTools

For a GUI solution [see here](https://rtech.support/books/troubleshooting-with-a-live-session/page/checking-the-health-of-disks)

You can check SMART in Linux using smartmonTools. The quick steps to get a report in Ubuntu are: (replace X with your desired disk)

```
sudo apt install smartmontools
sudo smartctl -a -d ata /dev/sdX
```

[More Info](https://help.ubuntu.com/community/Smartmontools)