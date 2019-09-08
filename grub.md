	load_video
	set gfxpayload=keep
	insmod gzio
	insmod part_gpt
	insmod fat
	if [ x$feature_platform_search_hint = xy ]; then
	  search --no-floppy --fs-uuid --set=root  CE2E-D441
	else
	  search --no-floppy --fs-uuid --set=root CE2E-D441
	fi
	echo	'Loading Linux linux ...'
	linux	/vmlinuz-linux root=UUID=5213db76-7598-4846-8309-bf64967101cb rw  loglevel=3 quiet
	echo	'Loading initial ramdisk ...'
	initrd	/initramfs-linux.img
  
  load_video
set gfxpayload=keep
insmod gzio
insmod part_gpt
insmod fat
if [ x$feature_platform_search_hint = xy ]; then
  search --no-floppy --fs-uuid --set=root  CE2E-D441
else
  search --no-floppy --fs-uuid --set=root CE2E-D441
fi
echo	'Loading Linux linux ...'
linux	/vmlinuz-linux root=UUID=5213db76-7598-4846-8309-bf64967101cb rw  loglevel=3 quiet
echo	'Loading initial ramdisk ...'
initrd	/initramfs-linux.img
