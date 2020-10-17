<ol>
	<li> /sbin/fdisk -lu ./lineage-16.0-20200713-rpi4.img </li>
	<li> 512 * startSector </li>
<li> sudo mount -o loop,offset=33554944 ./sdcard.img /mnt/rasp-pi-rootfs </li>
<li> sudo mkdir /mnt/rasp-pi-rootfs/home </li>
<li> sudo mkdir /mnt/rasp-pi-rootfs/home/pi </li>
<li> sudo cp {APPPATH}/{APPNAME} /mnt/rasp-pi-rootfs/home/pi </li>
<li> sudo chmod +x /mnt/rasp-pi-rootfs/home/pi/{APPNAME} </li>
<li> sudo nano /etc/X11/xinit/xinitrc

	/home/pi/{APPNAME} &
	matchbox-window-manager 
<li> sudo dd if=./sdcard.img of=/dev/mmcblk0 bs=1M status=progress </li>
<li> sync </li>

<li>  ./hellopi -platform linuxfb -display "LinuxFb:tty=/dev/fb1" </li>

</ol>
