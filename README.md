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

## Lesson2

<details>
<summary>Details</summary>

Домашнее задание: работа с mdadm

Задание
1. Добавить в виртуальную машину несколько дисков
2. Собрать RAID-0/1/5/10 на выбор
3. Сломать и починить RAID
4. Создать GPT таблицу, пять разделов и смонтировать их в системе.

Добавляем диски, проверяем, очищаем суперблоки:
```bash
user@ubuntu24:~$ lsscsi
[0:0:0:0]    disk    QEMU     QEMU HARDDISK    2.5+  /dev/sda
[3:0:0:1]    disk    QEMU     QEMU HARDDISK    2.5+  /dev/sdb
[4:0:0:2]    disk    QEMU     QEMU HARDDISK    2.5+  /dev/sdc
[5:0:0:3]    disk    QEMU     QEMU HARDDISK    2.5+  /dev/sdd
[6:0:0:4]    disk    QEMU     QEMU HARDDISK    2.5+  /dev/sde
[7:0:0:5]    disk    QEMU     QEMU HARDDISK    2.5+  /dev/sdf
user@ubuntu24:~$ sudo mdadm --zero-superblock --force /dev/sd{b,c,d,e,f}
mdadm: Unrecognised md component device - /dev/sdb
mdadm: Unrecognised md component device - /dev/sdc
mdadm: Unrecognised md component device - /dev/sdd
mdadm: Unrecognised md component device - /dev/sde
mdadm: Unrecognised md component device - /dev/sdf
```
Суперблоков нет т.к. диски новые и "чистые"

Создаём raid6 и проверяем:

```bash
user@ubuntu24:~$ sudo mdadm --create --verbose /dev/md0 -l 6 -n 5 /dev/sd{b,c,d,e,f}
mdadm: layout defaults to left-symmetric
mdadm: layout defaults to left-symmetric
mdadm: chunk size defaults to 512K
mdadm: size set to 1046528K
mdadm: Defaulting to version 1.2 metadata
mdadm: array /dev/md0 started.
user@ubuntu24:~$ sudo cat /proc/mdstat
Personalities : [raid0] [raid1] [raid4] [raid5] [raid6] [raid10] [linear]
md0 : active raid6 sdf[4] sde[3] sdd[2] sdc[1] sdb[0]
      3139584 blocks super 1.2 level 6, 512k chunk, algorithm 2 [5/5] [UUUUU]

unused devices: <none>
user@ubuntu24:~$ sudo mdadm -D /dev/md0
/dev/md0:
           Version : 1.2
     Creation Time : Mon Jul 13 21:46:44 2026
        Raid Level : raid6
        Array Size : 3139584 (2.99 GiB 3.21 GB)
     Used Dev Size : 1046528 (1022.00 MiB 1071.64 MB)
      Raid Devices : 5
     Total Devices : 5
       Persistence : Superblock is persistent

       Update Time : Mon Jul 13 21:46:49 2026
             State : clean
    Active Devices : 5
   Working Devices : 5
    Failed Devices : 0
     Spare Devices : 0

            Layout : left-symmetric
        Chunk Size : 512K

Consistency Policy : resync

              Name : ubuntu24:0  (local to host ubuntu24)
              UUID : 13621d63:2e8bedd4:c0df48d5:9f95eaf4
            Events : 17

    Number   Major   Minor   RaidDevice State
       0       8       16        0      active sync   /dev/sdb
       1       8       32        1      active sync   /dev/sdc
       2       8       48        2      active sync   /dev/sdd
       3       8       64        3      active sync   /dev/sde
       4       8       80        4      active sync   /dev/sdf
```
Ломаем массив:
```bash
user@ubuntu24:~$ sudo mdadm /dev/md0 --fail /dev/sde
mdadm: set /dev/sde faulty in /dev/md0
user@ubuntu24:~$ sudo cat /proc/mdstat
Personalities : [raid0] [raid1] [raid4] [raid5] [raid6] [raid10] [linear]
md0 : active raid6 sdf[4] sde[3](F) sdd[2] sdc[1] sdb[0]
      3139584 blocks super 1.2 level 6, 512k chunk, algorithm 2 [5/4] [UUU_U]

unused devices: <none>
user@ubuntu24:~$ sudo mdadm -D /dev/md0
/dev/md0:
           Version : 1.2
     Creation Time : Mon Jul 13 21:46:44 2026
        Raid Level : raid6
        Array Size : 3139584 (2.99 GiB 3.21 GB)
     Used Dev Size : 1046528 (1022.00 MiB 1071.64 MB)
      Raid Devices : 5
     Total Devices : 5
       Persistence : Superblock is persistent

       Update Time : Mon Jul 13 21:54:59 2026
             State : clean, degraded
    Active Devices : 4
   Working Devices : 4
    Failed Devices : 1
     Spare Devices : 0

            Layout : left-symmetric
        Chunk Size : 512K

Consistency Policy : resync

              Name : ubuntu24:0  (local to host ubuntu24)
              UUID : 13621d63:2e8bedd4:c0df48d5:9f95eaf4
            Events : 19

    Number   Major   Minor   RaidDevice State
       0       8       16        0      active sync   /dev/sdb
       1       8       32        1      active sync   /dev/sdc
       2       8       48        2      active sync   /dev/sdd
       -       0        0        3      removed
       4       8       80        4      active sync   /dev/sdf

       3       8       64        -      faulty   /dev/sde
```

Удаляем сломанный диск, затем добавляем его обратно и снаблюдаем ребилд:

```bash
user@ubuntu24:~$ sudo mdadm /dev/md0 --remove /dev/sde
mdadm: hot removed /dev/sde from /dev/md0
user@ubuntu24:~$ sudo mdadm /dev/md0 --add /dev/sde
mdadm: added /dev/sde
user@ubuntu24:~$ sudo cat /proc/mdstat
Personalities : [raid0] [raid1] [raid4] [raid5] [raid6] [raid10] [linear]
md0 : active raid6 sde[5] sdf[4] sdd[2] sdc[1] sdb[0]
      3139584 blocks super 1.2 level 6, 512k chunk, algorithm 2 [5/4] [UUU_U]
      [==============>......]  recovery = 74.9% (784944/1046528) finish=0.0min speed=261648K/sec

unused devices: <none>
user@ubuntu24:~$ sudo mdadm -D /dev/md0
/dev/md0:
           Version : 1.2
     Creation Time : Mon Jul 13 21:46:44 2026
        Raid Level : raid6
        Array Size : 3139584 (2.99 GiB 3.21 GB)
     Used Dev Size : 1046528 (1022.00 MiB 1071.64 MB)
      Raid Devices : 5
     Total Devices : 5
       Persistence : Superblock is persistent

       Update Time : Mon Jul 13 21:58:49 2026
             State : clean
    Active Devices : 5
   Working Devices : 5
    Failed Devices : 0
     Spare Devices : 0

            Layout : left-symmetric
        Chunk Size : 512K

Consistency Policy : resync

              Name : ubuntu24:0  (local to host ubuntu24)
              UUID : 13621d63:2e8bedd4:c0df48d5:9f95eaf4
            Events : 39

    Number   Major   Minor   RaidDevice State
       0       8       16        0      active sync   /dev/sdb
       1       8       32        1      active sync   /dev/sdc
       2       8       48        2      active sync   /dev/sdd
       5       8       64        3      active sync   /dev/sde
       4       8       80        4      active sync   /dev/sdf
```
Создаём GPT таблицу, разделы и монтируем их:

```bash
user@ubuntu24:~$ sudo parted -s /dev/md0 mklabel gpt
user@ubuntu24:~$ sudo parted /dev/md0 mkpart primary ext4 0% 20%
Information: You may need to update /etc/fstab.

user@ubuntu24:~$ sudo parted /dev/md0 mkpart primary ext4 20% 40%
Information: You may need to update /etc/fstab.

user@ubuntu24:~$ sudo parted /dev/md0 mkpart primary ext4 40% 60%
Information: You may need to update /etc/fstab.

user@ubuntu24:~$ sudo parted /dev/md0 mkpart primary ext4 60% 80%
Information: You may need to update /etc/fstab.

user@ubuntu24:~$ sudo parted /dev/md0 mkpart primary ext4 80% 100%
Information: You may need to update /etc/fstab.

user@ubuntu24:~$ for i in $(seq 1 5); do sudo mkfs.ext4 /dev/md0p$i;
> done
mke2fs 1.47.0 (5-Feb-2023)
Creating filesystem with 156672 4k blocks and 39200 inodes
Filesystem UUID: 586c95a8-5e4a-4a2b-a081-713d4dcf2a51
Superblock backups stored on blocks:
        32768, 98304

Allocating group tables: done
Writing inode tables: done
Creating journal (4096 blocks): done
Writing superblocks and filesystem accounting information: done

mke2fs 1.47.0 (5-Feb-2023)
Creating filesystem with 157056 4k blocks and 39280 inodes
Filesystem UUID: 9425d9cc-8849-4868-a6c0-6f734e641c0f
Superblock backups stored on blocks:
        32768, 98304

Allocating group tables: done
Writing inode tables: done
Creating journal (4096 blocks): done
Writing superblocks and filesystem accounting information: done

mke2fs 1.47.0 (5-Feb-2023)
Creating filesystem with 156672 4k blocks and 39200 inodes
Filesystem UUID: 459810be-d610-4727-ac1c-0406fd30bc56
Superblock backups stored on blocks:
        32768, 98304

Allocating group tables: done
Writing inode tables: done
Creating journal (4096 blocks): done
Writing superblocks and filesystem accounting information: done

mke2fs 1.47.0 (5-Feb-2023)
Creating filesystem with 157056 4k blocks and 39280 inodes
Filesystem UUID: 2cb9169e-d760-4f4f-9eea-a98a30317345
Superblock backups stored on blocks:
        32768, 98304

Allocating group tables: done
Writing inode tables: done
Creating journal (4096 blocks): done
Writing superblocks and filesystem accounting information: done

mke2fs 1.47.0 (5-Feb-2023)
Creating filesystem with 156672 4k blocks and 39200 inodes
Filesystem UUID: f5aa4a36-2ab8-4d36-92cd-a0b5a03e8a03
Superblock backups stored on blocks:
        32768, 98304

Allocating group tables: done
Writing inode tables: done
Creating journal (4096 blocks): done
Writing superblocks and filesystem accounting information: done
user@ubuntu24:~$ sudo mkdir -p /raid/part{1,2,3,4,5}
user@ubuntu24:~$ for i in $(seq 1 5); do sudo mount /dev/md0p$i /raid/part$i; done
user@ubuntu24:~$ df -hT
Filesystem                        Type   Size  Used Avail Use% Mounted on
tmpfs                             tmpfs  197M  1.1M  196M   1% /run
/dev/mapper/ubuntu--vg-ubuntu--lv ext4   9.8G  4.8G  4.5G  52% /
tmpfs                             tmpfs  981M     0  981M   0% /dev/shm
tmpfs                             tmpfs  5.0M     0  5.0M   0% /run/lock
/dev/sda2                         ext4   1.7G  209M  1.4G  13% /boot
tmpfs                             tmpfs  197M   12K  197M   1% /run/user/1001
/dev/md0p1                        ext4   586M   24K  543M   1% /raid/part1
/dev/md0p2                        ext4   587M   24K  544M   1% /raid/part2
/dev/md0p3                        ext4   586M   24K  543M   1% /raid/part3
/dev/md0p4                        ext4   587M   24K  544M   1% /raid/part4
/dev/md0p5                        ext4   586M   24K  543M   1% /raid/part5
```

</details>
