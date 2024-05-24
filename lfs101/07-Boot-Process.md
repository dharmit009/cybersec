# Linux Boot Process:

1. Power ON.
1. BIOS.
1. Master Boot Record (MBR) or EFI Partition.
1. Boot Loader (e.g. GRUB).
1. Kernel.
1. Initial RAM Disk - initramfs.
1. /sbin/init (parent process).
1. Command shell using getty.
1. Graphical User Interface (X window or wayland).

## Basic Input Output System (BIOS):

When the computer is powered on, the Basic Input/Output System (BIOS) initializes the hardware, including the screen and keyboard, and tests the main memory. **This process is also called POST (Power On Self Test).**

The BIOS software is stored on a read-only memory (ROM) chip on the motherboard. After this, the remainder of the boot process is controlled by the operating system (OS).

## Master Boot Record (MBR):

Once the POST is completed, system control passes from the BIOS to the boot loader. The boot loader is usually stored on one of the system’s storage devices, such as a hard disk or SSD drive, either in the boot sector (for traditional BIOS/MBR systems) or the EFI partition (for more recent (Unified) Extensible Firmware Interface or EFI/UEFI systems). Up to this stage, the machine does not access any mass storage media. Then, information on the date, time, and the most important peripherals are loaded from the CMOS values (A technology used for the battery-powered memory store, which allows the system to keep track of the date and time even when it is powered off).

A number of boot loaders exist for Linux, the most common ones are **GRUB** (for Grand Unified Boot loader), **ISOLINUX** (for booting from removable media), and DAS U-Boot (for booting on embedded devices/appliances). Most Linux boot loaders can present a user interface for choosing alternative options for booting Linux and even other operating systems that might be installed. When booting Linux, the boot loader is responsible for loading the kernel image and the initial RAM disk or filesystem (which contains some critical files and device drivers needed to start the system) into memory.

## Bootloader in Action:

The Bootloader has two distinct stages:

### BIOS / MBR SYSTEMS:
For systems using the BIOS/MBR method, the bootloader resides at the first sector of the hard disk, also known as the `Master boot record (MBR)`. The size of MBR is just 512 bytes. In this stage, the boot loader examines the partition table and **finds a bootable partition**. Once the bootable partition is detected, it then searches for the second stage bootloader for example **GRUB**, and loads it into RAM (Random Access Memory).

### UEFI SYSTEMS:

For systems using the EFI/UEFI method, UEFI firmware reads its Boot Manager data to determine which UEFI application is to be launched and from where (i.e., from which disk and partition the EFI partition can be found). The firmware then launches the UEFI application, for example GRUB, as defined in the boot entry in the firmware's boot manager. This procedure is more complicated but more versatile than the older MBR methods.

The second stage boot loader resides under `/boot`. A splash screen is displayed, which allows us to choose which operating system (OS) and/or kernel to boot. After the OS and kernel are selected, the boot loader loads the kernel of the operating system into RAM and passes control to it. Kernels are almost always compressed, so the first job they have is to uncompress themself. After this, it will check and analyze the system hardware and initialize any hardware device drivers built into the kernel.


