https://github.com/naelstrof/maim
maim -s | xclip -selection clipboard -t image/png
maim ~/Pictures/$(date +%s).png
maim -i $(xdotool getactivewindow) ~/mypicture.jpg
maim -u | feh -F - & maim -s -k cropped.png && kill $!
maim -s /tmp/screenshot.png; imgur /tmp/screenshot.png | xclip -selection clipboard
https://github.com/tremby/imgur.sh, xclip, xdotool