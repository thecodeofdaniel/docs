# How to start a Virtual Machine in Virt-Manager

## Put Virtual Machines in Custom Directory

- Such as...
  - `/home/user/VMs`

## Steps

- Create a new virtual machine
- Select `Local install media (ISO image or CDROM)`
- Select the ISO from custom directory
- Give custom CPUs and Memory
- Select `Select or create custom image` and then `Manage`
  - Click the `+` symbol in your custom VM directory to create a storage volume
    - Give name to .qcow2 file
    - Give custom storage size
    - Leave unchecked `Allocate entire volume now`
    - Click `Finish`
  - Click `Choose Volume`
- Click `Foward`
- Customize configuration if needed
- Click `Finish`
