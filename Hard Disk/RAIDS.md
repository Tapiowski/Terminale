## Create
df -hT // lsblk -o NAME,SIZE,FSTYPE,TYPE,MOUNTPOINT
sdc sdd sde

dd if=/dev/zero of=/dev/sda

sudo mdadm --create --verbose /dev/md0 --level=10 --raid-devices=3 /dev/sdc /dev/sdd /dev/sde

cat /proc/mdstat ## for progress

## Manage
https://www.digitalocean.com/community/tutorials/how-to-manage-raid-arrays-with-mdadm-on-ubuntu-22-04