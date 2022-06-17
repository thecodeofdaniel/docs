# Removing Swap Partition

## Pop!_OS

After deleting the encrypted swap partition you will be presented with a slow bootup time

In order to resolve this go to the

```
$ cd /etc/crypttab
```
There will be a line including `UUID`

Check if the `UUID` by using this command

```
$ lsblk -o NAME,SIZE,UUID,PARTUUID
```

`grep` the following with the `UUID` in the crypttab page

If it doesn't exist then remove that line in the file

<br />

### Note: The following may not be necessary

Comment out this line in the `fstab` file in the same directory `/etc`

`# /dev/mapper/cryptswap  none  swap  defaults  0  0`
