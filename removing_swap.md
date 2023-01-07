# Removing Swap Partition on Pop!_OS

- After deleting the encrypted swap partition you will be presented with a slow bootup time

- In order to resolve this, delete the contents in this file

        cd /etc/crypttab

- There will some text including a __UUID__
  - Something like this...
  - `cryptswap UUID=82fae514-4406-49c9-88e3-3a470dfcc030 /dev/urandom swap,plain,offset=1024,cipher=aes-xts-plain64,size=512`
- Before deleting, check if the __UUID__ exists using `lsblk`

        lsblk -o NAME,SIZE,UUID,PARTUUID
- If not, then delete the contents

## Edit the `/etc/fstab` file

- Comment out this line
  - `/dev/mapper/cryptswap  none  swap  defaults  0  0`
  