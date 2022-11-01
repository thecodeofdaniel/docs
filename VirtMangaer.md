# Notes about Virt-Manager

## Creating a VM
It's a good idea to create a storage volume in your custom storage pool
if you're going to start a VM

`Using the '+' symbol`

- Add a name to your VM in the format `qcow2`
- Add the capacity size
- Leave unchecked `Allocate entire volume now`
- Click `Finish`

## Adding an existing VM
When adding a VM, select `Import existing disk image`

- Provide the storage path
- Select the OS your installing
- Provide the RAM and number of CPUs cores
- Customize the install if you want
- Start the VM!