# Intro
I installed arch using the doggieOS guide on this github.

I did install kde as a backup but i installed sway on top of this while i work on completing the rice

I had a lot of problems with wifi on this install. In the past I was downgrading wpa_supplicant to fix this issue but I couldn't find the post that mentioned which version exactly so I found another fix this time which involved setting a kernel parameter.

# Fixing Wireless

$ lspci | grep Broadcom

03:00.0 Network controller: Broadcom Inc. and subsidiaries BCM43602 802.11ac Wireless LAN SoC (rev 01)

$ sudo micro /etc/default/grub

LINUX_DEFAULT="<blah> <blah> brcmfmac.feature_disable=0x82000"

This fixed whatever was preventing me from authenticating. It was still occasionally disconnecting though. I started using the network manager gui and selected save passsword for all users by the password field and that fixed it. Wifi good to go. Yay!

# sway basics
$ sudo pacman -S sway swaybg swayidle swaylock kitty

Copy default config over and set terminal before logging in.

sudo cp /etc/sway/config ~/.config/sway/config 

# XDG portal
Important for not getting really annoyed using sway. Read at least the frist paragraph of this wiki entry and install the following.
https://wiki.archlinux.org/title/XDG_Desktop_Portal
sudo pacman -S xdg-desktop-portal-wlr

# dunst
YOU NEED THIS, SILLY
- sudo pacman -S install dunst
- start in sway config file with line
- exec dunst
