# How to Create VM in Virt-Manager

## Tips

- Put VMs in custom directory such as...
  - `/home/user/VMs`
- and ISO's in
  - `/home/user/VMs/ISOs`

## Steps

- Choose how you would like to install the OS
  - Select `Local install media (ISO image or CDROM)`
  - Click `Foward`
- Choose ISO or CDROM install media
  - Click `Browse`
    - Select ISO
    - Click `Choose Volume`
  - Click `Foward`
- Give Custom CPUs and Memory
- Storage
  - Select `Select or create custom image` and then `Manage`
    - Click the `+` symbol for `Volumes` in your custom VMs directory
      - Give name to .qcow2 file
      - Give custom storage size
      - Leave unchecked `Allocate entire volume now`
      - Click `Finish`
    - Click `Choose Volume`
  - Click `Foward`
- Customize configuration if needed
- Click `Finish`

## Install VirtIO Drivers for Windows

- Turn off VM by shutting down Windows
  - Go to https://pve.proxmox.com/wiki/Windows_VirtIO_Drivers
    - Download the latest stable
    - Move ISO to appropriate directory
- Go back to VirtManager
  - Go to `Hardware Details` for VM
    - Select `SATA CDROM 1`
      - Change source path to the ISO you just downloaded
      - Click `Apply`
- Now run the VM
- Inside Windows
  - Open `File Explorer`
    - Select `This PC`
    - Open `CD Drive`
      - Run `virtio-win-guest-tools.exe`
        - Leave everything default and install
