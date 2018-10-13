# OCTO-PRINTER-CONTROLER
3D PRINTER OCTTO PRINTER CONTOLER PCB


1. DC 7~30V INPUT(DC12V or DC24V, 5V 4A OUT
2. PSU CONTROL( EXTERNAL RELAY CONTROL 12V or 24V Relay)
3. RGB LED CONTROL
4. Raspberry SPI TOUCH LCD SUPPORT


![v1 2_sch](https://user-images.githubusercontent.com/11598835/46899833-a0714800-ced3-11e8-9eae-bbafdd31d3e1.png)
![pcb_v1 2](https://user-images.githubusercontent.com/11598835/46899834-a2d3a200-ced3-11e8-92eb-150ee3ae9a74.png)

![v1 1_01](https://user-images.githubusercontent.com/11598835/46874394-075f1480-ce74-11e8-8775-5a9fb0a5c464.png)
LCD module Pi TFT 3.5 inch (320*480) Touchscreen Display Module
![v1 1_03](https://user-images.githubusercontent.com/11598835/46874435-2198f280-ce74-11e8-87f1-3caa8f3d6df9.png)
![v1 1_02](https://user-images.githubusercontent.com/11598835/46874464-31b0d200-ce74-11e8-94b3-80f0f6aa0f80.png)
![v1 1_06](https://user-images.githubusercontent.com/11598835/46874484-383f4980-ce74-11e8-96f9-7d96574cf30b.png)
![v1 1_v04](https://user-images.githubusercontent.com/11598835/46874488-3a090d00-ce74-11e8-8dbe-bd7b972c1a39.png)
![v1 1_v05](https://user-images.githubusercontent.com/11598835/46874495-3b3a3a00-ce74-11e8-9089-30a53a3ec9b9.png)
![v1 1_v07](https://user-images.githubusercontent.com/11598835/46874502-3d03fd80-ce74-11e8-87f4-e5af33d6ef59.png)
![v1 1_v10](https://user-images.githubusercontent.com/11598835/46874505-3e352a80-ce74-11e8-9f56-d8e30af4f5fd.png)


TOUCH GHI SETTING

OCTO PRINTER IMAGE DOWN LOAD

https://octoprint.org/download/

OCTO PRINTER IMAGE to SD MEMORY WRITE

https://www.raspberrypi.org/forums/viewtopic.php?t=131489
https://www.raspberrypi.org/forums/viewtopic.php?p=890408#p890408

sudo apt-get install --no-install-recommends xserver-xorg 

sudo apt-get install --no-install-recommends xinit 

sudo apt-get install raspberrypi-ui-mods

xwindos auto login setting

sudo raspi-config

3.Boot-option -> B1 Desktop /CLI -> B4 Desktop Autologin

TFT DRIVER INSTALL

https://www.waveshare.com/wiki/3.5inch_RPi_LCD_(A)#Method_1._Driver_installation

Wget https://www.waveshare.com/w/upload/1/1e/LCD-show-180817.tar.gz

DRIVER extractor

tar xvf LCD-show - *. tar.gz

cd LCD-show/

chmod 777 LCD35-show 

./LCD35-show


HDMI & TOUCH DRIVER INSTALL

https://www.raspberrypi.org/forums/viewtopic.php?t=175616
https://www.raspberrypi.org/forums/viewtopic.php?t=175616

sudo apt-get install xinput-calibrator

sudo nano /boot/config.txt

# Force use HDMI
hdmi_force_hotplug=1
# force a specific HDMI mode
hdmi_group=2
hdmi_mode=87

# custom display resolution (480x320 looks good , and 720x480 is not too bad too,3rd res is: 810x540 )
#         /----------------- Width: 480px ( or 720px /or 810px)
#         |   /------------- Height: 320px ( or 480px /or 540px)
#         |   |   /--------- Refresh: 60Hz
#         |   |   | /------- Aspect ratio: 6=15:9 (1=4:3, 2=14:9, 3=16:9, 4=5:4, 5=16:10)
#         |   |   | | /----- Margins: 0=disabled (1=enabled)
#         |   |   | | | /--- Interlace: 0=progressive (1=interlaced)
#         |   |   | | | | /- Reduced blanking: 0=normal (1=reduced)
#         |   |   | | | | |
hdmi_cvt 480 320 60 6 0 0 0

# uncomment to force a HDMI mode rather than DVI. This can make audio work in
# DMT (computer monitor) modes
hdmi_drive=2


CHROMIUM INSTALL

https://www.raspberrypi.org/forums/viewtopic.php?t=163316

sudo apt-get install unclutter

sudo apt-get install xdotool

sudo apt-get install chromium-browser –yes

CHROMIUM AUTO START SETTING

sudo nano ~/.config/lxsession/LXDE-pi/autostart

sudo -u pi chromium-browser --kiosk --incognito http://127.0.0.1 & 

sudo nano /boot/config.txt

sudo reboot

