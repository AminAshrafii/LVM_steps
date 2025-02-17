##lvm partition


1-
  # pvcreate  /dev/sdb
  
2-
  show pv
 ############################## pvdisplay

3- 
  Make Mount Permanent
Find the UUID of the new volume:
############################### blkid | grep /dev/opt-vg/opt-lv

4-
  Create a Volume Group (VG)
###############################  vgcreate opt-vg /dev/sdb
and
  for checking
############################### vgdisplay


5-
  Create a Logical Volume (LV)
############################### lvcreate -L 99G -n opt-lv opt-vg

Verify:
############################### lvdisplay

6-
  Format the Logical Volume
############################### mkfs.ext4 /dev/opt-vg/opt-lv


7-
  Create /opt Directory and Mount
############################### mount /dev/opt-vg/opt-lv /opt


  
