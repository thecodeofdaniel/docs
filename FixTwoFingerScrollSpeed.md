# Editing Two Finger Scroll Speed via "libinput"
`Option: "ScrollPixelDistance"`

### Find your device ID for your touchpad
        $ xinput
### List the properties from touchpad
        $ xinput list-props <device_id>

## How to change on the fly: 
        $ xinput set-prop <device_id> <sub_id> <value>
### Example     
        $ xinput set-prop 12 318 45         

# Make a Permanent Change

`Default value: 15`

        Section "InputClass"
                Identifier "libinput touchpad catchall"
                MatchIsTouchpad "on"
                MatchDevicePath "/dev/input/event*"
                Driver "libinput"
                Option "ScrollPixelDistance" "50"
        EndSection

### Find Similar Examples in
        /usr/share/X11/xorg.conf.d

## Put this code in directory
        /etc/X11/xorg.conf.d

### With a name such as
        39-libinput.conf
