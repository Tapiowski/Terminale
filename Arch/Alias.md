# Alias
alias v="nvim"
alias ls='ls --color=auto'
alias grep='grep --color=auto'
alias fps='xrandr --output DP-0 --mode 2560x1440 --rate 144'
alias parallel='sudo systemctl restart libvirtd.service'

# Git
alias gt="git -C /home/n1zk/Documents/Obsidian/Terminale add . && git -C /home/n1zk/Documents/Obsidian/Terminale commit -m 'Arch Sync - $(date)' && git -C /home/n1zk/Documents/Obsidian/Terminale pull && git -C /home/n1zk/Documents/Obsidian/Terminale push"
alias gm="git -C /home/n1zk/Documents/Obsidian/Medicina add . && git -C /home/n1zk/Documents/Obsidian/Medicina commit -m 'Arch Sync - $(date)' && git -C /home/n1zk/Documents/Obsidian/Medicina pull && git -C /home/n1zk/Documents/Obsidian/Medicina push"

# Functions
function lazygit() {
    git add .
    git commit -a -m "$1"
    git push
}
