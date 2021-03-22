# ZOOBAC INSTALALTION GUIDE

> ***This instruction assumes that all actions for preparing a usb flash drive will be performed in the
Windows operating system.***
____

**instruction in MS Word format:**
- [Linux Installation Instructions for UEFI COMPUTERS](src/Linux_Installation_Instructions_NEW_COMPUTERS.docx)
- [Linux Installation Instructions BIOS COMPUTERS](src/Linux_Installation_Instructions_OLD_COMPUTERS.docx)

____

**The whole task is divided into several points, namely:**

1. [Creating a bootable installation USB flash drive](#creating-a-bootable-installation-usb-flash-drive);
      - [Download sources](#download-sources)
      - make install flash drive:
          - [Computers with BIOS](#computers-with-bios)
          - [Computers with UEFI](#computers-with-uefi)
2. [Installation of the system](#installation-of-the-system);
3. [Setting up the system](#setting-up-the-system);
4. [Verification](#verification).

## Creating a bootable installation USB flash drive

### *Download sources*

- We need an image of the system that we will install. We chose Xubuntu (the system will be 64-bit). Download the [image](https://www.mirrorservice.org/sites/cdimage.ubuntu.com/cdimage/xubuntu/releases/20.04/release/xubuntu-20.04.2-desktop-amd64.iso) of the distribution. (**if the image does not work, take a newer version the image**)

- Then [the software](https://github.com/unetbootin/unetbootin/releases/download/647/unetbootin-windows-647.exe) to create a bootable USB flash drive.
- And [the archive](https://github.com/GetCider/zoobac_documentation/blob/master/src/zoobac.zip) files of the Zoobac .


### **We take the next step depending on the technology supported by a particular machine.**
___

#### **Computers with BIOS:**

- Run unetbootin, select the "Disk image" option and specify the path to the previously downloaded distribution.<p align="center"> 
  <img src="https://github.com/GetCider/zoobac_documentation/raw/master/imgs/old_pc_1.jpg" />
</p>

- **In this window, check that the program correctly identified your USB disk**

- Click **OK** and wait for the process to finish. After that we proceed to install the OS on our working host.

- Insert the created bootable USB flash drive into the usb connector and select "**boot from USB**" in the boot menu of the computer.

____

#### **Computers with UEFI:**

- Download rufus from https://rufus.ie/
- The “**Partition scheme**” and “**Target system**” should be as in the screenshot.
- **In this window, check that the program correctly identified your USB disk**
- Press **START** and wait for completion. After that we proceed to install the OS on our working host.

<p align="center"> 
  <img src="https://github.com/GetCider/zoobac_documentation/raw/master/imgs/new_pc_1.jpg" />
</p>
- Insert the created bootable USB flash drive into the usb connector and select "**boot from USB**" in the boot menu of the computer.

- When booting from a flash drive, select “**Try xubuntu**” and waiting for the system to boot
  

- An ESP can be created via a recent version of GParted (the Gparted version included in the system), and must have the following attributes:
  
       1. Mount point: /boot/efi (remark: no need to set this mount point when using the manual partitioning, the Ubuntu installer will detect it automatically)
       2. Size: minimum 100Mib. 200MiB recommended.
       3. Type: FAT32
       4. Other: needs a "boot" flag.

- Reboot the machine.

____

## Installation of the system

- Waiting for the live system to load and select the language and click "**Install Xubuntu**"
  
<p align="center"> 
  <img src="https://github.com/GetCider/zoobac_documentation/raw/master/imgs/installation1.png" />
</p>
### Steps of installation: 

1. Choose language, click "**Continue**".
2. In the next stеp click “**Continue**”
3. In the next step, select "Erase disk and install xubuntu" and click "**Install now**", in the window that appears, select "**Continue**".
4. Then select the timezone and press "**Continue**".
5. Select the layout and language and click "**Continue**".
6. In the next step, fill in the information about the user, the "**name**" field "**computer name**" and set the password.

**![#f03c15](https://via.placeholder.com/15/f03c15/000000?text=+) `!!!! Make sure to put a check on the item «login automatically» !!!`**

 7.  Click "**Continue**".
   
<p align="center"> 
  <img src="https://github.com/GetCider/zoobac_documentation/raw/master/imgs/installation2.png" />
</p>

8. Wait for the completion of the installation process. Then remove the installation flash drive and press "**restart now**".

____

## Setting up the system

- Unpack the contents of the archive zoobac.zip to **/home/zoobac/Desktop**
  
<p align="center"> 
  <img src="https://github.com/GetCider/zoobac_documentation/raw/master/imgs/installation3.png" />
</p>

- After the first system boot, click on the button with the mouse image (similar to the "**Start**" button in windows), select "**Settings**", and then "**Session and Startup**". In the "**Application Autostart**" tab, remove all the checkmarks.

- In the "**Application Autostart**" tab we click "**Add**", fill in the first two lines, and in the '**Command**' line  we specify the path to the executable file of our program. '**/home/zoobac/Desktop/desktop**'

<p align="center"> 
  <img src="https://github.com/GetCider/zoobac_documentation/raw/master/imgs/installation4.png" />
</p>
____

## Verification

That’s all, after rebooting of this computer, our software will always automatically start.

>If you make certain settings in the BIOS, the computer will automatically turn on when the power is applied to the power plug (useful in case when the electricity was turned off)

Now, we check the workability by rebooting the computer.

If computer refuses to see the system you will need to go to BIOS settings(F10 or F11 on Lenovo)
