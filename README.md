# linux-thinstation2.2.2i-config
 Config files for building thinstation 2.2.2i images for HP T5500 and HP T5530. The configuration includes the RDP connection from the terminal to the server, remote preview using VNC of the terminal, SSH access to the terminal and the Polish keyboard.

# Build
LANG=C ./build
> install the missing packages and libraries (names can be found in the errors displayed by the ./build command)

# Deploy in usbdrive/harddrive
1. Create new FAT partition.
2. Untar `boot-images/syslinux-everything.tar.gz` to new partition.
3. Copy thinstation.conf.user to `new partition/thinstation.profile/thinstation.conf.user`.
3. Run in windows syslinux.exe from new partiotion (copied in the previous point): `syslinux.exe -ma <drive letter>`.
> Only under the windows system is the -m option, which installs the appropriate mbr.
4. Boot from usbdrive/harddrive. 
> If it does not work, the fdisk application can manipulate CHS values - select the ones that will work with your computer. Sometimes you need to use compatibility mode with dos in fdisk when creating partitions
