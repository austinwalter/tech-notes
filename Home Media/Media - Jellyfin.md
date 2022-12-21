### Default Login
By default, the first user is called `jellyfin`, and if you didn't set a password in the wizard it will be empty.

### Stopping & Starting Server

Manage the Jellyfin system service with your tool of choice:
```
sudo service jellyfin status
sudo systemctl restart jellyfin
sudo /etc/init.d/jellyfin stop
```
[Reference](https://jellyfin.org/docs/general/administration/installing#ubuntu)

### Allowing External Drives to be recognized in Jellyfin Ubuntu

> I already made one comment, but I had an external/laptop setup w/Jellyfin a while back and it drove me crazy too, so I'll try and highlight the main problems I came across.

##### 1. Mounting the drives
> You said they were already mounted in `/media/<myuser>`, but if it ever becomes a problem you might need to configure your `/etc/fstab` file, which is used to automatically mount your drives to the filesystem.
>
> Use the command `lsblk` to see if your drives are already mounted and if they're not, to find the names of your partitions so you can mount them. Keep in mind, `sda` is the name of a drive, `sda1` is a partition.
> You need some identifying information other than partition names to mount them in fstab. You'll probably want to use the PARTUUID, which you can find with the command "blkid".

[Here's a link to the wiki explaining fstab](https://help.ubuntu.com/community/Fstab)

##### 2. Permissions

If you're going to have multiple services accessing your drives, it's probably a good idea to create a single user/group for convenience. Personally, I just call mine "media", but it's up to you.

```
sudo useradd media
```

Then add the user jellyfin to the media group.

```
sudo usermod -aG media jellyfin
```

You need the flag `-a` to add a group to a user without overwriting the others they're already in.

Next you need to make media the owner of all of your media files, and also set the correct permissions to those files.

```
sudo chown -R media:media /media/<myuser> && sudo chmod -R 775 /media/<myuser>
```

The `-R` flag makes both operations recursive, so they'll apply to any files or directories inside of `/media/<myuser>` as well.

##### Troubleshooting
> You know the reply I wrote yesterday? Well now it doesnt work hahahaha. Yesterday I added a library for the films and all was okay, now jellyfin user is in the media group and the media group is the owner the media files (at least I think so because I just repeated that step and didnt throw any error) and the film library doesnt work and can't add another to the disk, is like yesterday all over but you soution doesnt work. For the love of me I can't figure out why!!! Could you help me please? 🥲

> What's the output of `ls -la /path/to/films`?
>
>Also you can use the command `groups <user>` to double check that a certain user is in the right groups.

##### Listing Users

List Local Users
```
cut -d: -f1 /etc/passwd
```

List All Users
```
getent passwd
```

Add a User
```
sudo useradd <user>
```

[Reddit Reference Thread](https://www.reddit.com/r/jellyfin/comments/qderwx/allowing_external_drives_to_be_recognized_in/)

##### Undoing Ownership Change
Unfortunately you can't undo the changes made by chown or chmod. That's linux! Commands will actually do what you tell them to do. Better do a backup yourself next time.

However you can restore the default permissions for your home folder which will probably fix most of your issues.

First reset the owner of your home folder:

`sudo chown -Rv kpate352:kpate352 /home/kpate352/`
Then reset permissions for all files:

`find /home/kpate352/ -type f -print0 | xargs -0 sudo chmod -Rv 644`
Finally reset permissions for all folders:

`find /home/kpate352/ -type d -print0 | xargs -0 sudo chmod -Rv 755`
This should stabilise your situation.

[Reference](https://askubuntu.com/questions/1216137/undoing-chown-command)