# How to Change Username in Linux

## Things to take note of

- Ideally you should login as another user or login as root

## If Creating a New User

- Here's how...

        # usermod -aG sudo <username>

## Changing the Username

- Now in order to change the username

        # usermod -l <new_name> <old_name>

- In order to change the groups `<old_name>` was in to the new username

        # groupmod -n <new_name> <old_name>

- Confirm this by looking into old home directory of `<old_name>`

        ls -ld /home/<old_name>

- The owner and group owner should now be owned by `<new_name>`

## Change Username for Home Directory

- Here's how...

        # usermod -d /home/<new_name> -m <new_name>

- Check to confirm

        ls -ld /home/<new_name>

## Edit Username in GDM login screen

- Here's how...

        # usermod -c "<new_name>" <new_name>
