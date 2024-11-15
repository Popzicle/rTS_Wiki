---
layout: default
title: Installing Windows 10
nav_exclude: false
nav_order: 1
has_children: false
parent: OS Install Guides
search_exclude: false
last_modified_date: 2024-03-09
redirect_from: /books/how-to-and-guides/page/clean-installing-windows-10
---
{: .danger .danger-icon }
> All files on the drive you plan to install Windows to will be **deleted** if you follow this guide - this is intended. Please ensure you have an adequate [backup policy](/docs/backups) in place before proceeding if you have files of value.

# Prerequisites
* An internet connection.
* A working computer to run the Windows Media Creation Tool.
* A USB flash drive that is at least 8GB or greater.

# Part 1: Creating USB Installer

1. Using a USB flash drive **at least 8 gigabytes in size**, create a bootable USB flash drive using the [Media Creation Tool](https://www.microsoft.com/en-us/software-download/windows10) from Microsoft. This will also wipe any data stored on the USB flash drive.
   
    {: .warning .warning-icon }
    > Save MCT to Desktop or Downloads folder. MCT must be saved and run from outside the USB flash drive. Just moving an ISO file to the USB flash drive will not make it bootable.

2. Run MCT by double clicking it. You will be greeted with windows Terms Of Service, after reading it, press Accept.

     ![wintos.png](/assets/install-10/wintos.png)

3. Select create installation media for another PC, and then click next.

     ![aPC.png](/assets/install-10/aPC.png)

4. You can leave this to default, press next.  

     ![kde.png](/assets/install-10/kde.png)

5. Select USB flash drive, then press next.

     ![USB.png](/assets/install-10/USB.png)

6. Select the USB you want to use, press next. 

    {: .warning .warning-icon }
    > This step will wipe the selected USB Flash drive, so ensure you have nothing important on the USB drive, and back up all important documents.

     ![select.png](/assets/install-10/select.png)

7. Wait till MCT finish its job. this may take some time.

     ![downl.png](/assets/install-10/downl.png)

8. After MCT says it finished, shutdown your PC.

    {: .danger .danger-icon }
    > Disconnect all storage disks except from the main (C Drive) disk from the computer before installing Windows 10. Not doing so can accidentally wipe other disks or result in the installer choosing the wrong disk as the boot drive and putting actual windows on another drive.

# Part 2: Installing Windows 10

1. Boot into your USB that has the Windows 10 Media on it. 

    {: .info .info-icon }
    > You can do this by entering your systems' BIOS and change the BIOS boot order to have USB media as the first priority (this can usually be found under the boot tab), or simply look for the words "boot menu" when you see your BIOS boot screen, press the corresponding function key and choose the USB flash drive to boot from it.

2. Follow the steps on screen to install Windows 10.

3. Click Install now

     ![10-0.png](/assets/install-10/10-0.png)

4. Continue on until you hit the license key screen. Here you can either enter your license code or, if Windows has been installed to this computer before, click on the "I don't have a product key" link.

    ![10-1.png](/assets/install-10/10-1.png)

5. Continue on until you hit the “Which type of installation do you want?” screen. Click "Custom". 

    ![10-2.png](/assets/install-10/10-2.png)

6. Click on each partition of the target drive and select delete, once all the partitions are gone you will be left with unallocated space. At this point click `Next`.

    {: .danger .danger-icon }
    > If you see any drive other than "Drive 0" as seen in our images, power down and unplug the extra drives that you don't want to install windows on.

    {: .warning .warning-icon }
    > ***Each means ALL*** But do you mean ALL? ***Yes, All***. Once all the partitions are gone you will be left with unallocated space.

    ![10-3.png](/assets/install-10/10-3.png)

    ![10-4.png](/assets/install-10/10-4.png)



     {: .info .info-icon }
     > Ensure that you only have drive 0 partitions in this window before deleting, otherwise this means you didnt disconnect other drives as noted in step 8.


    <details markdown="1">
    <summary markdown=span>
    **Error: Windows cannot be installed on this disk. The selected disk has an MBR partition table.**

    </summary>

    > If you receive an error about your disk being MBR like this:
    >
    > [![the-selected-disk-has-an-mbr-partition-table-01.png](/assets/install-11/the-selected-disk-has-an-mbr-partition-table-01.png)](/assets/install-11/the-selected-disk-has-an-mbr-partition-table-01.png)
    > 
    >
    > then press `Shift+F10` to open CMD and follow below.
    > ```
    > diskpart
    > list disk
    > ```
    > 
    > [![Windows 11-2021-10-05-15-09-53.png](/assets/install-11/windows-11-2021-10-05-15-09-53.png)](/assets/install-11/windows-11-2021-10-05-15-09-53.png)
    >
    > [![Windows 11-2021-10-05-15-10-13.png](/assets/install-11/windows-11-2021-10-05-15-10-13.png)](/assets/install-11/windows-11-2021-10-05-15-10-13.png)
    >
    > [![Windows 11-2021-10-05-15-10-24.png](/assets/install-11/windows-11-2021-10-05-15-10-24.png)](/assets/install-11/windows-11-2021-10-05-15-10-24.png)
    >
    > [![Windows 11-2021-10-05-15-10-39.png](/assets/install-11/windows-11-2021-10-05-15-10-39.png)](/assets/install-11/windows-11-2021-10-05-15-10-39.png)
    >
    > Make note of the disk you want to install to from the step above.
    > ```
    > sel disk #
    > convert gpt
    > clean
    > ```
    > 
    > [![Windows 11-2021-10-05-15-10-51.png](/assets/install-11/windows-11-2021-10-05-15-10-51.png)](/assets/install-11/windows-11-2021-10-05-15-10-51.png)
    > [![Windows 11-2021-10-05-15-11-01.png](/assets/install-11/windows-11-2021-10-05-15-11-01.png)](/assets/install-11/windows-11-2021-10-05-15-11-01.png)
    > [![Windows 11-2021-10-05-15-11-13.png](/assets/install-11/windows-11-2021-10-05-15-11-13.png)](/assets/install-11/windows-11-2021-10-05-15-11-13.png)
    > 
    > You can exit the CMD and click `next` again.
    > [![Windows 11-2021-10-05-15-09-40.png](/assets/install-11/windows-11-2021-10-05-15-09-40.png)](/assets/install-11/windows-11-2021-10-05-15-09-40.png)

    </details>

7. Windows will now install. When it finishes it will automatically restart your machine, when your screen goes black pull out your installation USB drive.

{: .success .success-icon }
> Congratulations!
>
> You have successfully installed Windows 10. Once the computer has rebooted, you will be greeted with the Out-of-the-Box Experience and you can start setting up your new installation of Windows. 
