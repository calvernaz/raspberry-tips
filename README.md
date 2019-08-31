
Raspberry tips to easy development

## Enabling WiFi and SSH

Source: https://desertbot.io/blog/headless-raspberry-pi-3-bplus-ssh-wifi-setup

### Enabling SSH

	cd /run/media/<user>/boot/
	touch ssh

 ### Enabling WiFi

	cd /run/media/<user>/boot
	touch wpa_supplicant.conf

  edit `wpa.supplicant.conf`

	country=EU
	ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
	update_config=1

	network={
    	  ssid="NETWORK-NAME"
    	  psk="NETWORK-PASSWORD"
	}
	

sync and write

	 sudo sync /dev/sda1
	 umount /dev/sda1

## Disable bluetooth

	- /boot/config.txt

   	dtoverlay=pi3-disable-bt
		enable_uart=1

	- disable bluetooth

		sudo systemctl disable hciuart

	- remove references to serial0 from cmdline.txt (example below)

		dwc_otg.lpm_enable=0 console=tty1 root=/dev/mmcblk0p7 rootfstype=ext4 elevator=deadline fsck.repair=yes rootwait splash plymouth.ignore-serial-consoles
