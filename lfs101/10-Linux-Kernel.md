# The Linux Kernel:

The boot loader loads both the **kernel** and an **initial RAM–based file system (initramfs)** into memory, so it can be used directly by the kernel

When the kernel is loaded in RAM, it immediately initializes and configures the computer’s memory and also configures all the hardware attached to the system. This includes all processors, I/O subsystems, storage devices, etc. The kernel also loads some necessary user space applications.

Once the kernel has set up all its hardware and mounted the root filesystem, the kernel runs `/sbin/init`.
