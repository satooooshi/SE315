# SE315 -> ***[course material](https://ipads.se.sjtu.edu.cn/courses/os/)***
--------
### ***516413990003 SatoshiAIKAWA***
### ***2019/3/7***
## 1. prepare ubuntu  
---
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
git clone https://github.com/geofft/qemu.git -b 6.828-2.3.0
apt-get install libsdl1.2-dev
apt-get install libglib2.0-dev
apt-get install libz-dev
apt-get install libpixman-1-dev


cd qemu
sudo ./configure --prefix=/usr/local --target-list="i386-softmmu x86_64-softmmu"
OR
In case  error: 'g_mem_set_vtable' is deprecated
./configure --disable-werror --prefix=/usr/local --target-list="i386-softmmu x86_64-softmmu"

make
make install


fin.


