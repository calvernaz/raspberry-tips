# raspberry-tips
Raspberry tips to easy development

## enabling WiFi and SSH

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
