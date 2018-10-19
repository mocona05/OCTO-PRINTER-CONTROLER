# OCTO-PRINTER TFT-LCD SHIELD MOUDLE
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

RASPBERRY PI FIRMWARE UPDATE
sudo rpi-update

RASPBERRY PI UPDATE
sudo apt-get update 
sudo apt-get upgrade

RASPBERRY PI XWINDOWS INSTALL
sudo apt-get install --no-install-recommends xserver-xorg
sudo apt-get install --no-install-recommends xinit
sudo apt-get install raspberrypi-ui-mods

xwindos auto login & Pi camera setting
sudo raspi-config
3.Boot-option -> B1 Desktop /CLI -> B4 Desktop Autologin

![rpi-set01](https://user-images.githubusercontent.com/11598835/46899945-6f921280-ced5-11e8-8733-9a8a2dda06f3.png)

Pi CAMERA SETUP (Raspberry pi camera 사용시)
5. Interfacing Optin -> Pi Camera -> Yes
![rpi-set02](https://user-images.githubusercontent.com/11598835/47189405-57a80c00-d377-11e8-9879-542c8fbfb29b.png)

7.Advanced Options -> A1 Expand Filesystem
![rpi-set03](https://user-images.githubusercontent.com/11598835/47197200-98b41680-d39f-11e8-8927-1acf6e96e2c9.png)


TFT DRIVER INSTALL

https://www.waveshare.com/wiki/3.5inch_RPi_LCD_(A)#Method_1._Driver_installation


wget https://www.waveshare.com/w/upload/1/1e/LCD-show-180817.tar.gz

![consol1](https://user-images.githubusercontent.com/11598835/47189407-5971cf80-d377-11e8-8412-d9e97af0ed27.png)

DRIVER extractor

tar xvf LCD-show-180817.tar.gz
cd LCD-show/
chmod 777 LCD35-show 
./LCD35-show


HDMI & TOUCH DRIVER INSTALL

https://www.raspberrypi.org/forums/viewtopic.php?t=175616

sudo apt-get install xinput-calibrator



CHROMIUM INSTALL
sudo apt-get install unclutter
sudo apt-get install xdotool

https://raspberrypi.stackexchange.com/questions/374/how-do-i-install-google-chrome


sudo apt-get install chromium-browser

CHROMIUM AUTO START SETTING
https://www.raspberrypi.org/forums/viewtopic.php?t=163316

sudo nano ~/.config/lxsession/LXDE-pi/autostart
sudo -u pi chromium-browser --kiosk --incognito http://127.0.0.1 & 

![consol2](https://user-images.githubusercontent.com/11598835/47189410-5bd42980-d377-11e8-8e6b-21ce026a0bf3.png)


sudo reboot


PSU Control Plug In Setup

![gui01](https://user-images.githubusercontent.com/11598835/47196493-c26b3e80-d39b-11e8-9354-e4c18304e3d4.png)

LED Strip Control Plug in Setup

![gui02](https://user-images.githubusercontent.com/11598835/47196492-c1d2a800-d39b-11e8-8d63-ec137b7fc0e1.png)

TouchUI Plug in Setup

![gui03](https://user-images.githubusercontent.com/11598835/47196491-c1d2a800-d39b-11e8-8739-58778fd0eef6.png)

USB CAM Install(Option)

https://github.com/jacksonliam/mjpg-streamer/

sudo apt-get install subversion libjpeg8-dev libav-tools libv4l-dev cmake

git clone https://github.com/jacksonliam/mjpg-streamer.git

cd mjpg-streamer/mjpg-streamer-experimental

export LD_LIBRARY_PATH=.

sudo make

Connecting camera repeat command.

ls /dev/video* (If you see the / dev / video0, then everything should be fine, go ahead)

ttps://github.com/foosel/OctoPrint/wiki/MJPG-Streamer-configuration

sudo ./mjpg_streamer –i "./input_uvc.so –f 2 -y" -o "./output_http.so"

check at http://<your Raspberry pi's IP>:8080/?action=stream

![cam1](https://user-images.githubusercontent.com/11598835/47196489-c1d2a800-d39b-11e8-94b1-75423855fa21.png)


sudo usermod -a -G video pi
(to allow user access to a device video, it is necessary to add it to the appropriate group)
sudo make install
cd ~
sudo nano webcam-streamer

#!/bin/bash

Daemon=mjpg_streamer

DaemonBase=/usr/local

DaemonArgs="-i \"input_uvc.so –f 2 -y\" -o \"output_http.so\""

case "$1" in

start)

eval LD_LIBRARY_PATH=${DaemonBase}/lib ${DaemonBase}/bin/${Daemon} ${DaemonArgs} >/dev/null 2>&1 &

echo "$0: started"

;;
stop)

pkill -x ${Daemon}

echo "$0: stopped"

;;

*)

echo "Usage: $0 {start|stop}" >&2

;;

Esac

![cam02](https://user-images.githubusercontent.com/11598835/47197110-0b70c200-d39f-11e8-9a6b-62b13bd3cda5.png)


sudo chmod +x webcam-streamer
sudo mv webcam-streamer /usr/local/bin/

sudo nano ~/.octoprint/config.yaml

system:

  actions:
  
  - action: streamon
  
    command: sudo /usr/local/bin/webcam-streamer start
    
    confirm: false
    
    name: Start video stream
    
  - action: streamoff
  
    command: sudo /usr/local/bin/webcam-streamer stop
    
    confirm: false
    
    name: Stop video stream
    
![cam03](https://user-images.githubusercontent.com/11598835/47196496-c303d500-d39b-11e8-927a-436d0f93e258.png)

![cam04](https://user-images.githubusercontent.com/11598835/47196495-c26b3e80-d39b-11e8-9491-22dc55dee9ee.png)


Auto start cam

sudo nano /etc/rc.local

usr/local/bin/webcam-streamer start

(Just make sure to put it above the line that reads exit 0).

![cam05](https://user-images.githubusercontent.com/11598835/47196494-c26b3e80-d39b-11e8-9b17-26c75b5c6d32.png)




