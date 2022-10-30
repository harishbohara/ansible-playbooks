# What is this?

1. I have stored pre-compiled busybox ```initramfs``` here 
2. I also have a ```.config``` file to build ```linux-5.16.9``` 

I have tested everything with above builds. It will be easy to start again from where I have left.

---

### Build kernel
```shell
wget https://cdn.kernel.org/pub/linux/kernel/v5.x/linux-5.16.9.tar.xz
tar -xvf linux-5.16.9.tar.xz
cd linux-5.16.9

# Copy the ```.config``` from above  and past it here. Then build.
make -j $(nproc)
```
---


### Run it wil QEMU
```shell
sudo qemu-system-x86_64 -m 1G   -kernel vmlinux -initrd ~/initramfs.cpio.gz -hda /dev/zero -append "root=/dev/zero console=ttyS0" -serial stdio -display none  -netdev user,id=vmnic -device e1000,netdev=vmnic
```
