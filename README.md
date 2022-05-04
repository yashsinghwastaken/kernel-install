# [Kernel](https://kernel.org/)

Install `sudo apt-get install libncurses5-dev`


```bash
$ tar -xvf linux*.tar.xz
$ mv -rf linux* /usr/src/
# cd to the linux-kernel
$ make menuconfig
```
* Select `General Setup` and turn on 'Automatically append version information...'.
* Do whatever you want
* Save and exit
* A new file name `.config` was created

```bash
$ make kernelrelease
$ make 	# builds a kernel ready to be installed
$ make modules_install: # Installs all of the newly-built modules. They will now show up under a directory in `/lib/modules`
$ make install 	#  Install the new (compressed) kernel image into the `/boot` directory so that GRUB can find it at boot time. And it also create a new initrd initial ram disk that goes along with that kernel to support the early part of the boot process
```

make `.deb` file for debain and install the kernel
```dpkg-deb --build --root-owner-group <package-dir>```

```bash 
sudo dpkg -i *.deb
```
`reboot` into the new kernel
