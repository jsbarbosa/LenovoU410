# LenovoU410

## Ubuntu install (UEFI):

1. (Boot menu) Disable Intel Rapid Start, and Secure boot (create an admin password: 1234), select Boot Mode: UEFI.
2. If required create a EFI partition with 200 MB.
3. If the system doesn't start, boot using live USB. Install and run boot-repair.
```
sudo add-apt-repository ppa:yannubuntu/boot-repair
sudo apt-get update
sudo apt-get install -y boot-repair && boot-repair
```
4. Set the following advance configurations: purge and update GRUB
5. Mount the EFI partition: `sudo mount -t vfat /dev/sdb2 /mnt`
6. Copy the `*.efi` from ubuntu folder into `/boot`. `sudo cp /ubuntu/*.efi /boot`
7. Restart.
