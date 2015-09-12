# Kernels
In this repository you can find Arch Linux packages for 
- RT_preempt for the Beaglebone Black and Raspberry Pi 2
- Xenomai 3 for the Beaglebone Black


**Instructions**

1. In order to install Arch Linux on your Beaglebone Black or Raspberry Pi 2, you can follow the instructions at the [Arch Linux ARM](http://archlinuxarm.org/platforms) website.

2. You can either use the pre-compiled packages, or you can build them using the [makepkg](https://wiki.archlinux.org/index.php/Makepkg) utility. Simply `makepkg -s` will do the job.
You can set the `CROSS_COMPILE` variable, in case you want to do so. If so, keep in mind that you will have to modify the /etc/makepkg.conf to fit the ARM architecure. You can then install the package, by doing `pacman -U pkg-name`

3. This step is required only for those who want to use Xenomai. In order to install Xenomai (besides the custom Kernel), you need to configure it on the board. 
  * Do `git clone git://git.xenomai.org/xenomai-3.git`
  * `cd xenomai-3`
  * `./configure CFLAGS="-march=armv7-a -mfpu=vfp3" LDFLAGS="-march=armv7-a -mfpu=vfp3" --with-core=cobalt`


