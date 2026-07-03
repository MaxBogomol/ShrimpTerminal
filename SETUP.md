# raspi-config

`sudo raspi-config`

- i2c
- X11

# config

`sudo nano /boot/firmware/config.txt`
```
[all]
hdmi_group=2
hdmi_mode=87
hdmi_cvt 1024 600 60 6 0 0 0
dtoverlay=ads7846,cs=1,penirq=25,penirq_pull=2,speed=50000,keep_vref_on=0,swapxy=1,pmax=255,xohms=150,xmin=200,xmax=3900,ymin=200,ymax=3900

dtparam=i2c_arm=on
dtoverlay=i2c-rtc,ds3231

disable_splash=1
```

`sudo apt install xserver-xorg-input-evdev`  
`sudo nano /usr/share/X11/xorg.conf.d/45-evdev.conf` paste from 45-evdev.conf  
`sudo nano /usr/share/X11/xorg.conf.d/99-calibration.conf` paste from 99-calibration.conf

# RTC

`sudo apt install util-linux-extra`

`sudo nano /etc/rc.local`
```
/sbin/hwclock -s
exit0
```

`sudo nano /etc/default/hwcloc`
```
HWCLOCKACCESS=no
```

`sudo hwclock -r` read from rtc  
`sudo hwclock -w` set to rtc  
`sudo hwclock -s` set from rtc

# Print Screen

`sudo nano /etc/xdg/openbox/rpd-rc.xml`
```
scrot ~/Pictures/Screenshots/%Y-%m-%d-%H%M%S_\$wx\$h_scrot.png
```

# pi-apps

`sudo wget -qO- https://raw.githubusercontent.com/Botspot/pi-apps/master/install | bash`

- ZRAM (More RAM)
- Syncthing
- Screenshot
- Fastfetch
- Neofetch
- Arduino
- LibreOffice
- Gimp
- Inkscape
- Drawing
- Kolourpaint
- Celeste Classic

# apt apps

`sudo apt install onboard`  
`sudo apt install retroarch`

# flatpak apps

`sudo apt install flatpak`  
`flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo`  

`flatpak install flathub net.kuribo64.melonDS`  
`flatpak install flathub org.ppsspp.PPSSPP`  