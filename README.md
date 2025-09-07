# install termux 
from fdroid: https://f-droid.org/en/packages/com.termux/

# to install alpine

```
apt update ; apt upgrade ; apt install wget -y ; wget https://raw.githubusercontent.com/wahasa/Alpine/main/Install/alpine_3.21.sh ; chmod +x alpine_3.21.sh ; ./alpine_3.21.sh
```

# to install xfce

apk update
```
apk add --no-cache bash-completion openssl udev udisks2 xfce4 xfce4-screenshooter xfce4-screensaver xfce4-taskmanager xfce4-notifyd xfce4-terminal adw-gtk3 adwaita-xfce-icon-theme xfburn parole ristretto dbus-x11
```

# to setup vnc
install RVNC from playstore: https://play.google.com/store/apps/details?id=com.realvnc.viewer.android&hl=en

### install apt
```
apt install tigervnc xorg-xhost -y
```
### add script
```
echo "vncserver -geometry 1600x900 -listen tcp :1 && DISPLAY=:1 xhost +" > $PREFIX/bin/vncstart ; echo "vncserver -kill :1" > $PREFIX/bin/vncstop
```
### activate script
```
chmod +x $PREFIX/bin/vnc*
```
# add new session (2) and log in alpine

```
alpine ; apk add nano
```
### edit script
```
nano /usr/local/bin/vncstart
```
### add to it
```
#!/bin/sh
export DISPLAY=:1
export PULSE_SERVER=127.0.0.1
startxfce4
```

### ctrl + x, click Y enter.

activate it
```
chmod +x /usr/local/bin/vncstart
```
# run vnc server
### on session 1 and 2
type
```
vncstart
```
### to enter on RVNC
### click on + and type
```
:1
```
on address
# stop vnc server 
on 2 press [ctrl c , enter] (2x)
on 1 type
```
vncstop
```
# ;]
