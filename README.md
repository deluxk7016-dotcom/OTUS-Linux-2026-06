# Выполнение домашних работ по курсу OTUS - Администратор Linux. Продвинутый уровень
## Lesson1

<details>
<summary>Details</summary>
  
Описание домашнего задания

1) Запустить ВМ c Ubuntu.
2) Обновить ядро ОС на новейшую стабильную версию из mainline-репозитория.
3) Оформить отчет в README-файле в GitHub-репозитории.

Вывод терминала:
```bash
user@ubuntu24:~$ uname -r
6.8.0-134-generic
user@ubuntu24:~$ mkdir kernel && cd kernel
user@ubuntu24:~/kernel$ wget https://kernel.ubuntu.com/mainline/v7.1.3/amd64/linux-headers-7.1.3-070103-generic_7.1.3-070103.202607041245_amd64.deb
--2026-07-12 19:53:22--  https://kernel.ubuntu.com/mainline/v7.1.3/amd64/linux-headers-7.1.3-070103-generic_7.1.3-070103.202607041245_amd64.deb
Resolving kernel.ubuntu.com (kernel.ubuntu.com)... 185.125.189.74, 185.125.189.76, 185.125.189.75
Connecting to kernel.ubuntu.com (kernel.ubuntu.com)|185.125.189.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4095082 (3.9M) [application/x-debian-package]
Saving to: ‘linux-headers-7.1.3-070103-generic_7.1.3-070103.202607041245_amd64.deb’

linux-headers-7.1.3-070103-generic_7.1 100%[============================================================================>]   3.91M  6.94MB/s    in 0.6s

2026-07-12 19:53:23 (6.94 MB/s) - ‘linux-headers-7.1.3-070103-generic_7.1.3-070103.202607041245_amd64.deb’ saved [4095082/4095082]

user@ubuntu24:~/kernel$ wget https://kernel.ubuntu.com/mainline/v7.1.3/amd64/linux-headers-7.1.3-070103_7.1.3-070103.202607041245_all.deb
--2026-07-12 19:53:39--  https://kernel.ubuntu.com/mainline/v7.1.3/amd64/linux-headers-7.1.3-070103_7.1.3-070103.202607041245_all.deb
Resolving kernel.ubuntu.com (kernel.ubuntu.com)... 185.125.189.75, 185.125.189.74, 185.125.189.76
Connecting to kernel.ubuntu.com (kernel.ubuntu.com)|185.125.189.75|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 14860428 (14M) [application/x-debian-package]
Saving to: ‘linux-headers-7.1.3-070103_7.1.3-070103.202607041245_all.deb’

linux-headers-7.1.3-070103_7.1.3-07010 100%[============================================================================>]  14.17M  19.1MB/s    in 0.7s

2026-07-12 19:53:40 (19.1 MB/s) - ‘linux-headers-7.1.3-070103_7.1.3-070103.202607041245_all.deb’ saved [14860428/14860428]

user@ubuntu24:~/kernel$ wget https://kernel.ubuntu.com/mainline/v7.1.3/amd64/linux-image-unsigned-7.1.3-070103-generic_7.1.3-070103.202607041245_amd64.deb
--2026-07-12 19:53:58--  https://kernel.ubuntu.com/mainline/v7.1.3/amd64/linux-image-unsigned-7.1.3-070103-generic_7.1.3-070103.202607041245_amd64.deb
Resolving kernel.ubuntu.com (kernel.ubuntu.com)... 185.125.189.75, 185.125.189.74, 185.125.189.76
Connecting to kernel.ubuntu.com (kernel.ubuntu.com)|185.125.189.75|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17490112 (17M) [application/x-debian-package]
Saving to: ‘linux-image-unsigned-7.1.3-070103-generic_7.1.3-070103.202607041245_amd64.deb’

linux-image-unsigned-7.1.3-070103-gene 100%[============================================================================>]  16.68M  20.1MB/s    in 0.8s

2026-07-12 19:53:59 (20.1 MB/s) - ‘linux-image-unsigned-7.1.3-070103-generic_7.1.3-070103.202607041245_amd64.deb’ saved [17490112/17490112]

user@ubuntu24:~/kernel$ wget https://kernel.ubuntu.com/mainline/v7.1.3/amd64/linux-modules-7.1.3-070103-generic_7.1.3-070103.202607041245_amd64.deb
--2026-07-12 19:54:13--  https://kernel.ubuntu.com/mainline/v7.1.3/amd64/linux-modules-7.1.3-070103-generic_7.1.3-070103.202607041245_amd64.deb
Resolving kernel.ubuntu.com (kernel.ubuntu.com)... 185.125.189.75, 185.125.189.76, 185.125.189.74
Connecting to kernel.ubuntu.com (kernel.ubuntu.com)|185.125.189.75|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 170158272 (162M) [application/x-debian-package]
Saving to: ‘linux-modules-7.1.3-070103-generic_7.1.3-070103.202607041245_amd64.deb’

linux-modules-7.1.3-070103-generic_7.1 100%[============================================================================>] 162.28M  25.8MB/s    in 6.3s

2026-07-12 19:54:20 (25.9 MB/s) - ‘linux-modules-7.1.3-070103-generic_7.1.3-070103.202607041245_amd64.deb’ saved [170158272/170158272]

user@ubuntu24:~/kernel$ sudo dpkg -i *.deb
Selecting previously unselected package linux-headers-7.1.3-070103-generic.
(Reading database ... 76040 files and directories currently installed.)
Preparing to unpack linux-headers-7.1.3-070103-generic_7.1.3-070103.202607041245_amd64.deb ...
Unpacking linux-headers-7.1.3-070103-generic (7.1.3-070103.202607041245) ...
Selecting previously unselected package linux-headers-7.1.3-070103.
Preparing to unpack linux-headers-7.1.3-070103_7.1.3-070103.202607041245_all.deb ...
Unpacking linux-headers-7.1.3-070103 (7.1.3-070103.202607041245) ...
Selecting previously unselected package linux-image-unsigned-7.1.3-070103-generic.
Preparing to unpack linux-image-unsigned-7.1.3-070103-generic_7.1.3-070103.202607041245_amd64.deb ...
Unpacking linux-image-unsigned-7.1.3-070103-generic (7.1.3-070103.202607041245) ...
Selecting previously unselected package linux-modules-7.1.3-070103-generic.
Preparing to unpack linux-modules-7.1.3-070103-generic_7.1.3-070103.202607041245_amd64.deb ...
Unpacking linux-modules-7.1.3-070103-generic (7.1.3-070103.202607041245) ...
Setting up linux-headers-7.1.3-070103 (7.1.3-070103.202607041245) ...
Setting up linux-modules-7.1.3-070103-generic (7.1.3-070103.202607041245) ...
Setting up linux-headers-7.1.3-070103-generic (7.1.3-070103.202607041245) ...
Setting up linux-image-unsigned-7.1.3-070103-generic (7.1.3-070103.202607041245) ...
I: /boot/vmlinuz is now a symlink to vmlinuz-7.1.3-070103-generic
I: /boot/initrd.img is now a symlink to initrd.img-7.1.3-070103-generic
Processing triggers for linux-image-unsigned-7.1.3-070103-generic (7.1.3-070103.202607041245) ...
/etc/kernel/postinst.d/initramfs-tools:
update-initramfs: Generating /boot/initrd.img-7.1.3-070103-generic
/etc/kernel/postinst.d/zz-update-grub:
Sourcing file '/etc/default/grub'
Generating grub configuration file ...
Found linux image: /boot/vmlinuz-7.1.3-070103-generic
Found initrd image: /boot/initrd.img-7.1.3-070103-generic
Found linux image: /boot/vmlinuz-6.8.0-134-generic
Found initrd image: /boot/initrd.img-6.8.0-134-generic
Warning: os-prober will not be executed to detect other bootable partitions.
Systems on them will not be added to the GRUB boot configuration.
Check GRUB_DISABLE_OS_PROBER documentation entry.
Adding boot menu entry for UEFI Firmware Settings ...
done
user@ubuntu24:~/kernel$ ls -al /boot
total 206380
drwxr-xr-x  4 root root     4096 Jul 12 19:55 .
drwxr-xr-x 23 root root     4096 Jul  1 20:06 ..
-rw-------  1 root root  9128449 Jun 26 15:31 System.map-6.8.0-134-generic
-rw-------  1 root root 11899898 Jul  4 12:45 System.map-7.1.3-070103-generic
-rw-r--r--  1 root root   287560 Jun 26 15:31 config-6.8.0-134-generic
-rw-r--r--  1 root root   307299 Jul  4 12:45 config-7.1.3-070103-generic
drwxr-xr-x  5 root root     4096 Jul 12 19:55 grub
lrwxrwxrwx  1 root root       31 Jul 12 19:55 initrd.img -> initrd.img-7.1.3-070103-generic
-rw-r--r--  1 root root 75984798 Jul  1 20:07 initrd.img-6.8.0-134-generic
-rw-r--r--  1 root root 81182579 Jul 12 19:55 initrd.img-7.1.3-070103-generic
lrwxrwxrwx  1 root root       28 Jul  1 20:06 initrd.img.old -> initrd.img-6.8.0-134-generic
drwx------  2 root root    16384 Jul  1 20:04 lost+found
lrwxrwxrwx  1 root root       28 Jul 12 19:55 vmlinuz -> vmlinuz-7.1.3-070103-generic
-rw-------  1 root root 15042952 Jun 26 16:36 vmlinuz-6.8.0-134-generic
-rw-------  1 root root 17453568 Jul  4 12:45 vmlinuz-7.1.3-070103-generic
lrwxrwxrwx  1 root root       25 Jul  1 20:06 vmlinuz.old -> vmlinuz-6.8.0-134-generic
user@ubuntu24:~/kernel$
```

После перезагрузки:
```bash
user@ubuntu24:~$ uname -r
7.1.3-070103-generic
user@ubuntu24:~$
```
</details>
