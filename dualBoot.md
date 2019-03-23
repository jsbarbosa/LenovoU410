- [Multiple Boot Systems Time Conflicts](https://askubuntu.com/questions/169376/clock-time-is-off-on-dual-boot)

Create a file named `WindowsTimeFixUTC.reg` with the following contents and then double click on it to merge the contents with the registry:
```
Windows Registry Editor Version 5.00
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\TimeZoneInformation]
     "RealTimeIsUniversal"=dword:00000001
```

- [Reinstall GRUB](https://www.linuxdeveloper.space/install-windows-after-linux/)
```
lsblk -f
sudo mount /dev/sdaA /mnt/
sudo mount /dev/sdaB /mnt/boot
sudo mount --bind /dev /mnt/dev
sudo mount --bind /dev/pts /mnt/dev/pts
sudo mount --bind /proc /mnt/proc
sudo mount --bind /sys /mnt/sys

sudo chroot /mnt

grub-install /dev/sda (specify the disk `/dev/sdX`, not `/dev/sdaX`)
grub-install --recheck /dev/sdX
exit
```
