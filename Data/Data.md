# Recovery

lsblck discover disks
https://help.ubuntu.com/community/DataRecovery
ddrescue -r3 /dev/hda2 /dev/hdb2 logfile
e2fsck -v -f /dev/hdb2
mount -t ext2 -o ro /dev/hdb2 /mnt

gddrescue
Run gnuddrescue like this:
ddrescue [options] infile outfile [logfile]
So, if /dev/sda is unreadable, you will need to acquire another disk (or other media) onto which to save the output image. You will need to have more room on the new media than on the failed disk.
sudo ddrescue -r 3 /dev/sda /media/usbdrive/image /media/usbdrive/logfile
Run successive passes like this:
sudo ddrescue -r 3 -C /dev/sda /media/usbdrive/image /media/usbdrive/logfile

First you copy as much data as possible, without retrying or splitting sectors:
- ddrescue --no-split /dev/hda1 imagefile logfile 
Now let it retry previous errors 3 times, using uncached reads:
- ddrescue --direct --max-retries=3 /dev/hda1 imagefile logfile 
If that fails you can try again but retrimmed, so it tries to reread full sectors:
- ddrescue --direct --retrim --max-retries=3 /dev/hda1 imagefile logfile

---
# Raid
## Create
df -hT // lsblk -o NAME,SIZE,FSTYPE,TYPE,MOUNTPOINT
sdc sdd sde

dd if=/dev/zero of=/dev/sda (lento)

sudo mdadm --create --verbose /dev/md0 --level=10 --raid-devices=3 /dev/sdc /dev/sdd /dev/sde

cat /proc/mdstat ## for progress

## Manage
https://www.digitalocean.com/community/tutorials/how-to-manage-raid-arrays-with-mdadm-on-ubuntu-22-04

## Utils
sus
	Partition the disks that will be used with a slightly smaller capacity
	use /dev/sd?1
	`sgdisk --zap` ?

---
# LVM
https://www.digitalocean.com/community/tutorials/an-introduction-to-lvm-concepts-terminology-and-operations

https://wiki.ubuntu.com/Lvm install lvm2