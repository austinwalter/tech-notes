
```
sudo apt update
sudo apt upgrade
sudo reboot
sudo hostnamectl set-hostname <hostname>
```

Setup SSH
```
sudo apt -y install avahi-daemon
```

```
ssh <username>@<hostname>.local
```

https://ubuntu.com/tutorials/how-to-install-ubuntu-on-your-raspberry-pi#4-boot-ubuntu-server

## Mount An External Drive
https://help.ubuntu.com/community/Mount/USB

### 1. Get device info:

```
sudo fdisk -l
```

Determine Device Format
```
lsblk -n -o FSTYPE /dev/sdXX
```

### 2. Create the Mount Point
In the example below, the mount point name is “external”. You can name it anything you want.

```
sudo mkdir /media/external
```

for devices formatted in FAT16 or FAT32:
```
sudo mount /dev/sdXX /media/external
```

for devices formatted in ntfs:
```
sudo mount -t ntfs-3g /dev/sdXX /media/external
```

### 3. Unmounting the Drive
When you are finished with the device, don't forget to unmount the drive before disconnecting it. Assuming `/dev/sdb1` is mounted at `/media/external`, you can either unmount using the device or the mount point:

```
sudo umount /dev/sdb1
```
or:
```
sudo umount /media/external
```

## Automount a Drive
https://askubuntu.com/questions/783061/automount-in-16-04

First get device info:
```
lsblk
```

Note the device id of the disk to be mounted, for example ‘sda1'. Then we need the UUID of the disk to be mounted, find it with the code below replacing sdXX with the correct device id from the previous step:
```
blkid /dev/sdXX
```

The UUID looks like this:
```
40e554eb-6421-4813-88ea-3882a3a7a153
```

Now open this file:
```
sudo nano /etc/fstab
```

Now add this line to the end, changing the UUID for yours and /mnt/Disk should be changed to where you want to mount the disk:
```
UUID=40e554eb-6421-4813-88ea-3882a3a7a153 /mnt/Disk auto nosuid,nodev,nofail,x-gvfs-show 0 0
```

Ctrl+X, then ‘Y' to save and exit.


## Share the Drive
Now it's time to share that drive on your network, so you can add your files and access them from any device in the house. To do this, we're going to use a tool called Samba, which is an open-source implementation of Windows' SMB/CIFS file-sharing protocol. It's not your only option for sharing files, but it's easy to set up and compatible with just about any system you might have on the network, so it's what I recommend.

Raspbian doesn't come with Samba installed by default, so you'll need to make sure your repositories are up to date and install it with the following commands:
```
sudo apt install samba samba-common
```

The installer will ask if you want to modify smb.conf to use WINS settings from DHCP. Choose Yes and press Enter. Now you edit that configuration file yourself, to share your drive. Run:
```
sudo vim /etc/samba/smb.conf
```

Then, from the command-line text editor that appears, use your arrow key to scroll to the bottom of the document. You'll want to add a block of text that looks something like this:
```
[MyMedia]
path = /media/external/
writeable = yes
create mask = 0775
directory mask = 0775
public=no
```
### Create a Password and Add Users
Finally, you'll need to create a password for Samba so you can see your share from other machines. (There are ways to configure Samba without requiring a password, but this generally isn't good security practice, so I recommend adding a password.) To add a password to the existing Pi user, run:

```
sudo smbpasswd -a <username>
```

Enter your desired password when prompted—it doesn't have to be the same as your user password on the Pi itself, but it can be—and press Enter.

You can add other users with sudo adduser jeff, where jeff is the user you want to add, and run sudo smbpasswd -a jeff to give that user their own password. This isn't strictly necessary, but it can be useful if you have multiple people in your household to whom you want to give different read and write permissions on certain shares.

Once that's all done, run the following command to restart Samba:
```
sudo systemctl restart smbd
```

Now you should be able to access your media

### source:
https://www.pcmag.com/how-to/how-to-turn-a-raspberry-pi-into-a-nas-for-whole-home-file-sharing

## rsync

### source:
https://www.digitalocean.com/community/tutorials/how-to-use-rsync-to-sync-local-and-remote-directories