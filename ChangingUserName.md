# How to Change username in Linux

Ideally you should login as another user with sudo permissions
(I believe you can login as root in order to perform these actions as well)


## If you're going to login as another user

Use this command to do so

```# usermod -aG sudo <username>```

## Changing Username

Now in order to change the username

```# usermod -l <new_name> <old_name> ```

In order to change the groups `<old_name>` was in to the new username

```# groupmod -n <new_name> <old_name> ```

Confirm this by looking into old home directory of `<old_name>`

```$ ls -ld /home/<old_name>```

The owner and group owner should now be owned by `<new_name>`

## How to change username for Home Directory

```# usermod -d /home/<new_name> -m <new_name> ```

Check to confirm

```$ ls -ld /home/<new_name> ```


## Editing username in GDM login screen

```# usermod -c "<new_name>" <new_name>```

## Your Done!
