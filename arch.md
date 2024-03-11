# Arch

**硬盘分区**

`cfdisk /dev/sda`

gpt

efi空间100~200M（EFI System）

剩下给根分区（Linux root （x86-64））

记得type后write一下

**分区格式化及确认**

`mkfs.fat /dev/sda1`

`mkfs.ext4 /dev/sda2`

`lsblk`


**挂载分区及确认**

`mount /dev/sda2 /mnt`

`mkdir -p /mnt/boot/EFI`

`mount /dev/sda1 /mnt/boot/EFI`

`lsblk`

**安装系统（需要联网）**

`pacstrap /mnt base linux linux-firmware dhcpcd vim`

**生成 fstab 文件**

`genfstab -U /mnt >>/mnt/etc/fstab`

`cat /mnt/etc/fstab`


**切换新安装的系统**

`arch-chroot /mnt`

`passwd`


**添加普通用户**

`useradd -m -G wheel -s /bin/bash *username*`

`passwd *username*`


**Grub引导**

`pacman -S grub efibootmgr`

`grub-install --target=x86_64-efi --efi-directory=/boot/EFI`

`grub-mkconfig -o /boot/grub/grub.cfg`


**退出并进入系统**

`exit`

`reboot`