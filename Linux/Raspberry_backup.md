# Create Raspberry backup images

## Create image
* Locate drive label: `sudo fdisk -l`
* Unmount all sdcard devices: `sudo umount <sdcard>/<device>`
  * example: `sudo umount /dev/sdb/sdb1`
* Copy sdcard: `sudo dd if=<sdcard> of=raspberry_backup.img status=progress`
  * example: `sudo dd if=/dev/sdb of=raspberry_backup.img status=progress` 

### (optional) Reduce image partition size
For installing on smaller sdcards
* Mount image: `sudo losetup -P /dev/loop0 raspberry_backup.img`
* Open on gparted: `sudo gparted /dev/loop0`
* Reduce second partition size and close gparted
* Unmount image: `sudo losetup -d /dev/loop0`
* Check the end sector of the second partition: `sudo fdisk -l raspberry_backup.img`
* Truncate image file to the end sector: `truncate -s $(((END+1)*512)) raspberry_backup.img`
  * Example: `truncate -s $(((30201855+1)*512)) raspberry_backup.img`

## Compress image
* Compress with zip: `zip -8 raspberry_backup.img.zip raspberry_backup.img`
