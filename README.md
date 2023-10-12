# vrm_update
This is a binary script to update the VRM of certain N9K-SUP-A+ and N9K-SUP-B+ to fix bug CSCwd65255

How to use:

1. upload the file "S99vrm_update.bin" to /tmp directory of the active supervisor
2. login as root (Cisco TAC assistance required)
3. change permission
4. run the script

lab example:
pod2-spine150# whoami

root

pod2-spine150# chmod +x /tmp/S99vrm_update.bin

pod2-spine150#

pod2-spine150# ls -l /tmp/S99vrm_update.bin
-rwx------ 1 root root 22056 Sep 21 15:44 /tmp/S99vrm_update.bin
pod2-spine150#
pod2-spine150# /tmp/S99vrm_update.bin
Thu Sep 21 15:44:31 PDT 2023 RUNNING /tmp/S99vrm_update.bin

If the spine has standby supervisor, please follow below steps:

1. On the active supervisor, copy the file S99vrm_update.bin to /bootflash/
2. Console into standby supervisor and login as root
3. copy the script from active sup bootflash to standby sup /tmp directory
4. change permission
4. run the script

lab example:
(none)# whoami
root
(none)# cp /bootflash-remote/S99vrm_update.bin /tmp
(none)# chmod +x /tmp/S99vrm_update.bin
(none)# ls -la /tmp/S99vrm_update.bin
-rwx------ 1 root root 22056 Sep 21 22:50 /tmp/S99vrm_update.bin
(none)# /tmp/S99vrm_update.bin
Thu Sep 21 22:50:35 UTC 2023 RUNNING /tmp/S99vrm_update.bin
