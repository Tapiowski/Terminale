thunderbird
awesome
picom
xscreensaver
zsh
yay -- software manager
rsync
rofi -- launcher
obsidian && anki
nmap
neovim
unzip
alacritty
fsl - mri
htop OR btop
zathura PDF
feh PNG
mpv MOV
yt-dlp YT
locate - find
nftables OR etables?
[[maim]] - screenshot
cbonsai, fortune cowsay
p7zip
## font
grep stl /usr/share/fonts/local/fonts.dir
fc-cache -vf
fc-list
fc-match NameOfFont -s
?
## services
[[systemctl]]

## virtual machine
https://www.makeuseof.com/how-to-install-arch-linux-kvm-configure-virtual-machine/

## os install
https://www.blackarch.org/downloads.html
	root:blackarch
	sudo dd bs=512M status=progress if=file.iso of=/dev/sdX
	https://www.blackarch.org/blackarch-install.html
grub-mkconfig -o /boot/grub/grub.cfg
/etc/default/grub file that reads: GRUB_DISABLE_OS_PROBER=false. install os-prober