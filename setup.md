# SE315   
-> reference here ***[course material](https://ipads.se.sjtu.edu.cn/courses/os/)***
--------
### ***516413990003 SatoshiAIKAWA***
### ***2019/3/7***
## 1. prepare ubuntu  
---
### environment
docker image ubuntu:1604 -> [reference here](https://weblabo.oscasierra.net/docker-ubuntu1604/)  
uname -a  
Linux e7c82da0c343 4.9.125-linuxkit #1 SMP Fri Sep 7 08:20:28 UTC 2018 x86_64 x86_64 x86_64 GNU/Linux

doceker image push しとく！！

https://weblabo.oscasierra.net/docker-ubuntu1604/


docker run -it -d -v /Users/satoshiaikawa/os2019/dev:/home/stu/devlop --name ubuntu1604 ubuntu:16.04 
docker exec -it ubuntu1604 /bin/bash

docker start ubuntu1604
docker stop ubuntu1604
docker rm ubuntu1604

## 2. setup qemu
https://pdos.csail.mit.edu/6.828/2018/tools.html
https://blog.csdn.net/eye_water/article/details/80638463

(VPN server switch to france auto mode)
cd
apt-get update
objdump -i
gcc -m32 -print-libgcc-file-name  
apt-get install gcc-multilib  
apt-get install git  
HasError//git clone https://github.com/geofft/qemu.git -b 6.828-2.3.0   
NoError//***clone http://web.mit.edu/ccutler/www/qemu.git -b 6.828-2.3.0***
apt-get install libsdl1.2-dev  
apt-get install libglib2.0-dev  
apt-get install libz-dev  
apt-get install libpixman-1-dev  


cd qemu
sudo ./configure --prefix=/usr/local --target-list="i386-softmmu x86_64-softmmu"
OR
In case  error: 'g_mem_set_vtable' is deprecated
./configure --disable-werror --prefix=/usr/local --target-list="i386-softmmu x86_64-softmmu"
OR in case

(process:11100): GLib-WARNING **: /build/glib2.0-7ZsPUq/glib2.0-2.48.2/./glib/gmem.c:483: custom memory allocation vtable not supported
qemu-system-i386 -drive file=obj/kern/kernel.img,index=0,media=disk,format=raw -serial mon:stdio -gdb tcp::25000 -D qemu.log 

(process:11103): GLib-WARNING **: /build/glib2.0-7ZsPUq/glib2.0-2.48.2/./glib/gmem.c:483: custom memory allocation vtable not supported
Could not initialize SDL(No available video device) - exiting
GNUmakefile:156: recipe for target 'qemu' failed
make: *** [qemu] Error 1   
***TRY THIS!!!!
https://blog.csdn.net/eye_water/article/details/80638463  
clone http://web.mit.edu/ccutler/www/qemu.git -b 6.828-2.3.0  
./configure --disable-kvm --disable-sdl --target-list="i386-softmmu x86_64-softmmu"***

make  
make install


fin.


