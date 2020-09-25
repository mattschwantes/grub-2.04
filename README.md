# grub-2.04
Credit/license/source:  Originally obtained from grub-2.04.tar.gz at https://git.savannah.gnu.org/cgit/grub.git 

All licenses and credits are theirs. I merely host this to add a small change necessary for Linux efistub booting on Surface RT/2 (maybe other EFI ARM32 devices).

Build instructions:

0. git clone https://www.github.com/coherixmatts/grub-2.04
1. cd into <grub-2.04> directory
2. ./bootstrap
3. ./configure --with-platform=efi --target=arm-linux-gnueabihf
4. make
5. cd <grub-2.04>/grub-core
6. grub-mkimage -O arm-efi -d . -o grub.efi -p / part_gpt part_msdos ntfs ntfscomp hfsplus fat ext2 normal chain boot configfile linux gfxterm videoinfo efi_gop all_video video video_fb loadenv help reboot raid6rec raid5rec mdraid1x mdraid09 lvm diskfilter zfsinfo zfscrypt gcry_rijndael gcry_sha1 zfs true test sleep search search_fs_uuid search_fs_file search_label png password_pbkdf2 gcry_sha512 pbkdf2 part_apple minicmd memdisk lsacpi lssal lsefisystab lsefimmap lsefi disk keystatus jpeg iso9660 halt gfxterm_background gfxmenu trig bitmap_scale video_colors bitmap font fshelp efifwsetup echo terminal gettext efinet net priority_queue datetime bufio cat btrfs gzio lzopio crypto acpi extcmd mmap
7. it's very fast - the compiled grub.efi should now be in the <grub-core> directory


NOTES:

These instructions were tested on an Ubuntu 14.04 x64 system.  They are not 100% step-by-step instructions. Some modules and dependencies are missing. The error messages in terminal will make clear what you need to apt-get install.
