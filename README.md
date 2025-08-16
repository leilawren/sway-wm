# basics
I installed arch using the doggieOS guide on this github.

I did install kde as a backup but i installed sway on top of this while i work on completing the rice

I had a lot of problems with wifi on this install. In the past I was downgrading wpa_supplicant to fix this issue but I couldn't find the post that mentioned which version exactly so I found another fix this time which involved setting a kernel parameter.

fixing it

$ lspci output

03:00.0 Network controller: Broadcom Inc. and subsidiaries BCM43602 802.11ac Wireless LAN SoC (rev 01)

$ sudo micro /etc/default/grub

add kernel parameter: brcmfmac.feature_disable=0x82000

LINUX_DEFAULT="blah blah blah parameter'

# sway basics
$ sudo pacman -S sway swaybg swayidle swaylock

reboot and get into sway from sddm

# XDG portal
https://wiki.archlinux.org/title/XDG_Desktop_Portal

sudo pacman -S xdg-desktop-portal-wlr
