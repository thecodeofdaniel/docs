# How to Enable Hibernation on Pop!_OS

## Create a Swap File

- Create the swap file

        sudo fallocate -l <#>G /swapfile

- Set the permissions to file

        sudo chmod 600 /swapfile

- Format as swap

        sudo mkswap /swapfile

- Activate the swap

        sudo swapon /swapfile

- Add swap to /etc/fstab file

        echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab

## Configuration

- Get __UUID__ of the swap file
  - It should look somethings like this
  - `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`

            findmnt -no UUID -T /swapfile

- Get __Offset__ of the swap file
  - It should look something like this
  - `xxxxxxx..`

            sudo filefrag -v /swapfile | awk '{ if($1=="0:"){print $4} }'

## Update Kernel Options

- Kernel stub

        sudo kernelstub -a "resume=UUID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx resume_offset=xxxxxxx"

- Add below line to /etc/initramfs-tools/conf.d/resume. Create the file if not present

        resume=UUID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx resume_offset=xxxxxxxxxxxx

- Update the configurations

        sudo update-initramfs -u

## Test

- Hibernate

        sudo systemctl hibernate

## Add "Hibernate" Option

- Add extension
  - Add manually from command line
  - Install extension manager

### Add Manually

- Get extension's __UUID__

        unzip -c ~/Downloads/openweather-extension@jenslody.de.v94.shell-extension.zip metadata.json | grep uuid

  - UUID: `openweather-extension@jenslody.de`

- Create the Destination Directory

        mkdir -p ~/.local/share/gnome-shell/extensions/openweather-extension@jenslody.de

- Unzip GNOME Extension

        unzip -q ~/Downloads/openweather-extension@jenslody.de.v94.shell-extension.zip -d ~/.local/share/gnome-shell/extensions/openweather-extension@jenslody.de/

- Restart GNOME Shell
  - Press \<Alt\> + \<F2\>, then enter `r` to restart

- Open the GNOME extensions app and enable

### Install extension manager

- Install

        sudo apt install gnome-shell-extension-manager

- Look for the extension and `install` it

## Install "System Action - Hibernate"