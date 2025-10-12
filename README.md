# debian-on-asus-c101p


Debian on Asus C101 - see also wiki for extra background and sources

. Download Cadmium Bob GRU image
https://github.com/Maccraft123/Cadmium/releases

. flash to card

. activate wifi
ip -a #look for device name

ip link set [device_name] up
nmtui
click activate and find right wifi-point

. expand filesystem
sudo apt install cloud-guest-utils && sudo apt install f2fs-tools && sudo growpart /dev/sda 3 

. reboot into other debian install (/dev/sda3 cannot be mounted when resizing)
sudo resize.f2fs /dev/sda3

. apt install sudo  # install sudo 
. edit config file to bookworm instead of Sid

. ./install-to-here # choose no Desktop

. choose bookworm
. apt update && apt upgrade
. sudo apt install gnome-core --install-recommends gnome-terminal gnome-tweaks gnome-shell-extension-dashtodock fonts-ubuntu git

REBOOT

. Fix keybind to make function keys working
sudo apt-get -y install curl; curl -LOk https://github.com/fascinatingcaptain/CBFixesAndTweaks/archive/master.tar.gz; tar -zxvf master.tar.gz; cd CBFixesAndTweaks-master; sudo -E bash CBFixesAndTweaks.sh

. Install macos cursor
https://github.com/ful1e5/apple_cursor/releases/download/v2.0.1/macOS.tar.xz
cd macOS && sudo mv macOS /usr/share/icons

. Install WhiteSur theme
https://github.com/vinceliuice/WhiteSur-gtk-theme

Dependencies
sudo apt install sassc libglib2.0-dev libxml2-utils 	# dependencies
git clone https://github.com/vinceliuice/WhiteSur-gtk-theme.git --depth=1 && cd White*

./install.sh &&./install.sh -l && sudo ./tweaks.sh -g && ./tweaks.sh -f && ./tweaks.sh -d 	# install ; fix libadwaita, tweak gdm, firefox, dash to dock

. install Yaru icons
sudo apt install yaru-theme-icon

. install extension logo menu
https://extensions.gnome.org/extension/4451/logo-menu/

. install plymouth
