*Rimanete aggiornati sui nostri social:*
- [Discord Offensive Security Italia](https://discord.gg/FEjgBMdAeA)
- [Twitter Roby7979](https://twitter.com/ModernNaval)
- [Canale Youtube Roby7979](https://www.youtube.com/channel/UCAwPX5amsoJBiJyj-vmHhcQ)
- [Canale Twitch Roby7979](https://www.twitch.tv/roby7979)

# Linux-personalizzazione-professionale-Hacking-Etico
## Video #1 - [Installazione Distro e VM](https://youtu.be/zYgN2Ty16RA?si=APubWMo8LlyM6LXo)
## Video #2 - [Download Repository e configurazione](https://youtu.be/IjkOhg1RBow?si=zsooCDTLL98EC0wC)
## Video 3# - [Configurando la kitty e Feh](https://youtu.be/5LUnpIeTxLA?si=ss4NK6lfGaHr833m)
## Video 4# - [La Polybar](https://youtu.be/H4PjrwGDDQg?si=liucgmOdsCcOfo96)
## Video 5# - [Powerlevel10k](https://youtu.be/kKWzyok9gDM?si=eykZupXpFgSJRrhP)
## Video #6 - [Batcat e Lsd](https://youtu.be/hqTVwAXyK8M)
## Video #7 - [Configurazione Polybar](https://youtu.be/kO68cV8F-eU?si=Nvp46bUOfsVd2U4o)
## Video #8 - [Ultimi Plugins, riepilogo tasti](https://youtu.be/ZwyI13z0gDc?si=3BDV2V-1Ez4HHbHq)


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

git clone --recursive https://github.com/polybar/polybar 

### 1.mkdir build
### 2.cd build
### 3.cmake ..
### 4.make -j$(nproc)
### 5.sudo make install



# 3.PICOM E ROFI
apt install meson libxext-dev libxcb1-dev libxcb-damage0-dev libxcb-xfixes0-dev libxcb-shape0-dev libxcb-render-util0-dev libxcb-render0-dev libxcb-composite0-dev libxcb-image0-dev libxcb-present-dev libxcb-xinerama0-dev libpixman-1-dev libdbus-1-dev libconfig-dev libgl1-mesa-dev libpcre2-dev libevdev-dev uthash-dev libev-dev libx11-xcb-dev libxcb-glx0-dev

git clone https://github.com/ibhagwan/picom.git

### 1.git submodule update –-init -–recursive 
### 2.meson –-buildtype=release . build 
### 3.ninja -C build
### 4.sudo ninja -C build install

apt install rofi

# 4. SCRIPT PER VIDEO n.3

Color.ini

cursor_shape          Underline
cursor_underline_thickness 1
window_padding_width  20

Special
foreground #a9b1d6
background #1a1b26

Black
color0 #414868
color8 #414868

Red
color1 #f7768e
color9 #f7768e

Green
color2  #73daca
color10 #73daca

Yellow
color3  #e0af68
color11 #e0af68

Blue
color4  #7aa2f7
color12 #7aa2f7

Magenta
color5  #bb9af7
color13 #bb9af7

Cyan
color6  #7dcfff
color14 #7dcfff

White
color7  #c0caf5
color15 #c0caf5

Cursor
cursor #c0caf5
cursor_text_color #1a1b26

Selection highlight
selection_foreground #7aa2f7
selection_background #28344a


----------------------

KITTY.CONFIG

enable_audio_bell no

include color.ini

font_family HackNerdFont
font_size 13

disable_ligatures never

url_color #61afef

url_style curly

map ctrl+left neighboring_window left
map ctrl+right neighboring_window right
map ctrl+up neighboring_window up
map ctrl+down neighboring_window down

map f1 copy_to_buffer a
map f2 paste_from_buffer a
map f3 copy_to_buffer b
map f4 paste_from_buffer b

cursor_shape beam
cursor_beam_thickness 1.8

mouse_hide_wait 3.0
detect_urls yes

repaint_delay 10
input_delay 3
sync_to_monitor yes

map ctrl+shift+z toggle_layout stack
tab_bar_style powerline

inactive_tab_background #e06c75
active_tab_background #98c379
inactive_tab_foreground #000000
tab_bar_margin_color black

map ctrl+shift+enter new_window_with_cwd
map ctrl+shift+t new_tab_with_cwd

background_opacity 0.95

shell zsh

Invia un messaggio in "Video #3 Personalizazzione Linux"


