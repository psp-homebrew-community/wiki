---
layout: default
title: Dumping Games
---
# Dumping Games

You can back up your physical UMD games to your Memory Stick or PC. This helps
your games load faster and saves your UMD drive from wearing out. 

Transferring backups over to a PC, or any device PPSSPP runs on also lets you
emulate your games!

## Prerequisites

Make sure you have these ready:

- A PSP running firmware 6.61.
- ARK custom firmware installed.
- A Memory Stick with *at least 2* GB of free space.
- (optionally) A mini USB cable for your computer.

## The PC Method (Fastest)

The easiest way to dump a game is to use your PSP as a disc drive. Your PC will
read the UMD directly over USB.

1.  Put your UMD into the PSP.
2.  Press Select on the main menu to open the VSH Menu.
3.  Find the USB Device option and change it from Memory Stick to UMD Disc.
4.  Close the menu and connect your PSP to your PC with the USB cable.
5.  Go to Settings and select USB Connection on the PSP.
6.  Your computer will mount the PSP like a CD drive. You will see a single `.iso`
    file inside.
7.  Drag that file to your computer.

But remember to change the USB Device back to Memory Stick when you finish.

## On-Device Dumping

You can dump games directly to your Memory Stick without a PC. UMD Image
Creator or PSP Filer v6.6 have been tested and are generally the go-to. 

Dont bother with tools like USBSSS because they often produce broken dumps.

### Using [UMD Image Creator](https://github.com/saramibreak/UmdImageCreator)[]()

This app handles weird disc formats better than most tools.

1.  Install UMD Image Creator and launch it.
2.  Insert your game disc.
3.  Press Circle to start the process.
4.  Wait for it to finish.
5.  Press Triangle to exit.

Your new ISO file will be sitting in the `ms0:/ISO/` folder.

### Using [PSP Filer](https://www.gamebrew.org/wiki/PSP_Filer)[]()

Filer is an older file manager homebrew that happens to include a ripping tool.

1.  Copy the Filer folder to `ms0:/PSP/GAME/`.
2.  Open PSP Filer from your game list.
3.  Press Triangle to open the main menu.
4.  Press the Right Trigger to choose UMD Ripping.
5.  Press Start and let it run.
6.  Press Home and quit the app when it finishes.

Your new ISO file will be sitting in the ms0:/ISO/ folder.

