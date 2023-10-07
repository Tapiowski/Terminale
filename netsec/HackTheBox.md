## 1
blob:https://app.hackthebox.com/cec4cf28-48fb-48fa-83d4-4ea2fd76c798
sudo [[openvpn]] server.ovpn
ping target
[[nmap]] -sV target
open telnet port, search google, access service
admin, administrator, root
user.txt, root.txt, flag.txt
b40abdfe23665f766f9c61ecba8a4c19

## 2
[[ping]] 10.129.118.2
[[FTP]], 21 [[port]] since not using encryption, [[MitM]]
enumeration nmap -sV
foothold ftp, anonymous pass random, help shows commands, get flag.txt
035db21c881520061c53e0536e44f815

# 3
[[smb]], https://academy.hackthebox.eu/module/details/34
### enumeration
nmap -sv
active share:
135/tcp [[msrpc]] (share folder) [[smbclient]]
139/tcp [[netbios-ssn]]
[[smbclient]] -L 10.129.127.92 needs username, uses local if not provided
press enter at pass request
shows 4 shares: ADMIN\$, C\$, IPC\$ not browsable, WorkShares
### foothold
```
smbclient \\\\10.129.127.92\\WorkShares 
```
[[ls]]: listing contents of the directories within the share  
[[cd]]: changing current directories within the share  
[[get]]: downloading the contents of the directories within the share  
[[exit]]: exiting the smb shel
exfil 5f61c10dffbc77a704d76016a22f1664