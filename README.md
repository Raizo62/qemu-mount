# qemu-mount - Tools for mounting QEMU images

These tools allow it to inspect and modify QEMU images within Linux.
Internally they use qemu-nbd, the QEMU Disk Network Block Device Server.
That takes a VM disk image, supported by QEMU, and exports it as a
NBD device. This NBD device can be mounted and then used as any
other disk. It needs no extra packages, just QEMU.

The qemu-mount scripts hide the use of NBD, they offer a similar
interface as the normal mount tools. The scripts can be used as a
normal user, the privileged commands are then started with sudo.

## qemu-part - show partition table

qemu-part shows the partition table of a qemu image, just use
`qemu-part <qemu_image>`.

## qemu-mount - mount QEMU image

qemu-mount has the following usage:
```
Usage: qemu-mount [OPTIONS] qemu_image mount_point

Options:
  -p partition_number      select, which partition to mount, default #1
  -r                       mount read-only
  -t fstype                set filesystem type
  -o mount_options         additional mount options
  -u                       set owner to current user
```

Without arguments it prints a list of mounted images.

## qemu-umount - unmount mounted QEMU image

The usage of qemu-umount is simple,
`qemu-umount <qemu_image or mount_point>`.
