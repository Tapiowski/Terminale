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
`sudo grub-probe -t fs_uuid -d /dev/sda1`
`/etc/grub.d/40_custom` followed by `sudo update-grub`
```
menuentry "Windows 10" {
insmod part_gpt
insmod fat
insmod search_fs_uuid
insmod chain
search --fs-uuid --no-floppy --set=root XXXXXXXXX
chainloader (${root})/efi/Microsoft/Boot/bootmgfw.efi
}
```
Normally `grub-mkconfig` should auto-detect dual booted operating systems (via the `os-prober` utility)
```
$ mkdir -p /mnt/windows
$ mount /dev/sda1 /mnt/windows
$ grub-mkconfig -o /boot/grub/grub.cfg
```
https://kb.adamsdesk.com/operating_system/create_a_bootable_windows_10_usb_using_linux/