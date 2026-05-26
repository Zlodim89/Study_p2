"Данный README.md предназначен для предосталвения отчета по выполненному домашнему заданию "С чего начинается Linux""
Занятие 1. Обновление ядра системы
Цель домашнего задания
Научиться обновлять ядро в ОС Linux.
Описание домашнего задания
1) Запустить ВМ c Ubuntu.
2) Обновить ядро ОС на новейшую стабильную версию из mainline-репозитория.
3) Оформить отчет в README-файле в GitHub-репозитории.

Выполнение задания:

toor@ubuntu24021:~$ uname -r
6.8.0-117-generic

toor@ubuntu24021:~$ mkdir kernel
toor@ubuntu24021:~$ cd kernel/
toor@ubuntu24021:~/kernel$ wget https://kernel.ubuntu.com/mainline/v6.18.32/amd64/linux-headers-6.18.32-061832-generic_6.18.32-061832.202605191520_amd64.deb
toor@ubuntu24021:~/kernel$ wget https://kernel.ubuntu.com/mainline/v6.18.32/amd64/linux-headers-6.18.32-061832_6.18.32-061832.202605191520_all.deb
toor@ubuntu24021:~/kernel$ wget https://kernel.ubuntu.com/mainline/v6.18.32/amd64/linux-image-unsigned-6.18.32-061832-generic_6.18.32-061832.202605191520_amd64.deb	
toor@ubuntu24021:~/kernel$ wget https://kernel.ubuntu.com/mainline/v6.18.32/amd64/	linux-modules-6.18.32-061832-generic_6.18.32-061832.202605191520_amd64.deb
sudo dpkg -i *.deb 

toor@ubuntu24021:~/kernel$ ls -al /boot
total 214020
drwxr-xr-x  4 root root     4096 May 26 00:23 .
drwxr-xr-x 23 root root     4096 May 25 22:49 ..
-rw-r--r--  1 root root   304142 May 19 15:20 config-6.18.32-061832-generic
-rw-r--r--  1 root root   287605 May  5 13:53 config-6.8.0-117-generic
drwxr-xr-x  5 root root     4096 May 26 00:23 grub
lrwxrwxrwx  1 root root       28 May 25 22:49 initrd.img -> initrd.img-6.8.0-117-generic
-rw-r--r--  1 root root 79593880 May 26 00:23 initrd.img-6.18.32-061832-generic
-rw-r--r--  1 root root 76305433 May 25 22:52 initrd.img-6.8.0-117-generic
lrwxrwxrwx  1 root root       33 May 26 00:23 initrd.img.old -> initrd.img-6.18.32-061832-generic
drwx------  2 root root    16384 May 25 22:40 lost+found
-rw-------  1 root root 10563177 May 19 15:20 System.map-6.18.32-061832-generic
-rw-------  1 root root  9127090 May  5 13:53 System.map-6.8.0-117-generic
lrwxrwxrwx  1 root root       25 May 25 22:49 vmlinuz -> vmlinuz-6.8.0-117-generic
-rw-------  1 root root 16765440 May 19 15:20 vmlinuz-6.18.32-061832-generic
-rw-------  1 root root 15034760 May  5 15:56 vmlinuz-6.8.0-117-generic
lrwxrwxrwx  1 root root       30 May 26 00:23 vmlinuz.old -> vmlinuz-6.18.32-061832-generic

toor@ubuntu24021:~/kernel$ sudo update-grub
Sourcing file `/etc/default/grub'
Generating grub configuration file ...
Found linux image: /boot/vmlinuz-6.18.32-061832-generic
Found initrd image: /boot/initrd.img-6.18.32-061832-generic
Found linux image: /boot/vmlinuz-6.8.0-117-generic
Found initrd image: /boot/initrd.img-6.8.0-117-generic
Warning: os-prober will not be executed to detect other bootable partitions.
Systems on them will not be added to the GRUB boot configuration.
Check GRUB_DISABLE_OS_PROBER documentation entry.
Adding boot menu entry for UEFI Firmware Settings ...
done

toor@ubuntu24021:~$ uname -r 
6.18.32-061832-generic


