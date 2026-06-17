---
layout: default
title: Fixing "corrupted" Memory Sticks
---

Have you ever had those moments when your SD card just *randomly* out of nowhere becomes unreadable and you cant transfer files to it anymore / write to it?

Has happened to mee too, as such - below guide.

On linux you can use fsck(1) to fix "corrupted" Memory Sticks - you'll need to find a way to mount the card you have (usually an Micro SD card inside an adapater) to your computer.
Please note that this part of the guide is only for **Linux** - for the *Windows* parts of the guide, please see **here**.

I've added EMOJIS to point you to look at the warnings, please *actually* read them as, if you fuck up - we can't help you.

# On Linux
### Finding Your SD Card
⚠️ **WARNING** ⚠️

If you pick the wrong drive here, there's a real possiblity to cause ❗ **IRREVERSIBLE** ❗ damage to your *main partition* / other drives.

Take five seconds to check the storage size before running any repair or format commands.


1. Unplug your SD Card from the adapter.
2. Run this:
   `lsblk`
3. Plug the SD Card back into the adapter.
4. Run it again:
   `lsblk`
5. Look at the listing, they should differ and the *new* entry is your SD Card. It usually shows up as `mmcblk0` or something like `sdb` or `sdc`. Make sure that *you're NOT looking at any of your main drives* !


### Fixing the Partition

Once you have the exact partition name (ie; mmcblk0p1 ), you can repair it -  just replace mmcblk0p1 in the steps below with your actual partition name (that you've made SURE is none of your main drives).

First, unmount the drive:

`sudo umount /dev/mmcblk0p1`

Next, run the FAT repair tool - this is automatic:

`sudo fsck.fat -a /dev/mmcblk0p1`

If you prefer to take a look what's broken and approve manually, use this:

`sudo fsck.fat -r /dev/mmcblk0p1`
