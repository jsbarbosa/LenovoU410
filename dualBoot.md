- [Multiple Boot Systems Time Conflicts](https://askubuntu.com/questions/169376/clock-time-is-off-on-dual-boot)

Create a file named `WindowsTimeFixUTC.reg` with the following contents and then double click on it to merge the contents with the registry:
```
Windows Registry Editor Version 5.00
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\TimeZoneInformation]
     "RealTimeIsUniversal"=dword:00000001
```

- [Reinstall GRUB](https://howtoubuntu.org/how-to-repair-restore-reinstall-grub-2-with-a-ubuntu-live-cd)
```
lsblk -f
sudo mount /dev/sdXY /mnt/
sudo mount --bind /dev /mnt/dev && sudo mount --bind /dev/pts /mnt/dev/pts && sudo mount --bind /proc /mnt/proc && sudo mount --bind /sys /mnt/sys

sudo chroot /mnt

grub-install /dev/sdX (specify the disk `/dev/sdX`, not `/dev/sdaX`)
grub-install --recheck /dev/sdX

update-grub

exit
```
