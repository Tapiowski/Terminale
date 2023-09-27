lsblck discover disks
https://help.ubuntu.com/community/DataRecovery
ddrescue -r3 /dev/hda2 /dev/hdb2 logfile
e2fsck -v -f /dev/hdb2
mount -t ext2 -o ro /dev/hdb2 /mnt

---

gddrescue

Run gnuddrescue like this:

ddrescue [options] infile outfile [logfile]

So, if /dev/sda is unreadable, you will need to acquire another disk (or other media) onto which to save the output image. You will need to have more room on the new media than on the failed disk.

sudo ddrescue -r 3 /dev/sda /media/usbdrive/image /media/usbdrive/logfile

Run successive passes like this:

sudo ddrescue -r 3 -C /dev/sda /media/usbdrive/image /media/usbdrive/logfile

---

First you copy as much data as possible, without retrying or splitting sectors:

- ddrescue --no-split /dev/hda1 imagefile logfile 
    

Now let it retry previous errors 3 times, using uncached reads:

- ddrescue --direct --max-retries=3 /dev/hda1 imagefile logfile 
    

If that fails you can try again but retrimmed, so it tries to reread full sectors:

- ddrescue --direct --retrim --max-retries=3 /dev/hda1 imagefile logfile
