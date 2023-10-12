# Linux-personalizzazione-professionale-Hacking-Etico
## Video #1 - Installazione Distro e VM https://youtu.be/zYgN2Ty16RA?si=APubWMo8LlyM6LXo
## Video #2 - Download Repository e configurazione
## Video 3# - 


# 1.SCRIPT RESIZE:
#!/usr/bin/env dash

if bspc query -N -n focused.floating > /dev/null; then
	step=20
else
	step=100
fi

case "$1" in
	west) dir=right; falldir=left; x="-$step"; y=0;;
	east) dir=right; falldir=left; x="$step"; y=0;;
	north) dir=top; falldir=bottom; x=0; y="-$step";;
	south) dir=top; falldir=bottom; x=0; y="$step";;
esac

bspc node -z "$dir" "$x" "$y" || bspc node -z "$falldir" "$x" "$y"



# 2.POLYBAR:
apt install cmake cmake-data pkg-config python3-sphinx libcairo2-dev libxcb1-dev libxcb-util0-dev libxcb-randr0-dev libxcb-composite0-dev python3-xcbgen xcb-proto libxcb-image0-dev libxcb-ewmh-dev libxcb-icccm4-dev libxcb-xkb-dev libxcb-xrm-dev libxcb-cursor-dev libasound2-dev libpulse-dev libjsoncpp-dev libmpdclient-dev libuv1-dev libnl-genl-3-dev

git clone –recursive https://github.com/polybar/polybar [Son 2 guiones donde pone ‘recursive‘]

mkdir build
cd build
cmake ..
make -j$(nproc)
sudo make install



# 3.PICOM E ROFI
apt install meson libxext-dev libxcb1-dev libxcb-damage0-dev libxcb-xfixes0-dev libxcb-shape0-dev libxcb-render-util0-dev libxcb-render0-dev libxcb-composite0-dev libxcb-image0-dev libxcb-present-dev libxcb-xinerama0-dev libpixman-1-dev libdbus-1-dev libconfig-dev libgl1-mesa-dev libpcre2-dev libevdev-dev uthash-dev libev-dev libx11-xcb-dev libxcb-glx0-dev

git clone https://github.com/ibhagwan/picom.git

git submodule update –init –recursive [Son 2 guiones donde pone ‘init‘ y ‘recursive‘]
meson –buildtype=release . build [Son 2 guiones donde pone ‘buildtype‘] 
ninja -C build
sudo ninja -C build install

apt install rofi

