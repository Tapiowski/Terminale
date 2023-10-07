thunderbird
awesome
zsh
yay -- software manager
rsync
rofi -- launcher
obsidian
nmap
neovim
nitrogen - background, useless
mv - useless
calibre - useless
unzip
alacritty
fsl - mri
htop
picom
zathura PDF
feh PNG
mpv MOV
yt-dlp YT
locate - find

https://github.com/naelstrof/maim
	maim -s | xclip -selection clipboard -t image/png
	maim ~/Pictures/$(date +%s).png
	maim -i $(xdotool getactivewindow) ~/mypicture.jpg
	maim -u | feh -F - & maim -s -k cropped.png && kill $!
	maim -s /tmp/screenshot.png; imgur /tmp/screenshot.png | xclip -selection clipboard
	https://github.com/tremby/imgur.sh, xclip, xdotool

## pacman
pacman -S
pacman -Ss search

## font
```
grep stl /usr/share/fonts/local/fonts.dir
```
fc-cache -vf
```
fc-list
```
```
fc-match NameOfFont -s
```