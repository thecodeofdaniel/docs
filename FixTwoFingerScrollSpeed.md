# Editing Two Finger Scroll Speed via "libinput"

`Option: "ScrollPixelDistance"`

## Find the Device __ID__ for Touchpad

        xinput

## List the Properties

        xinput list-props <device_id>

## Change the Scroll Speed

        xinput set-prop <device_id> <sub_id> <value>

### Example

        xinput set-prop 12 318 45

## Make a Permanent Change

- Add this piece of code to a file in this directory
  - `/etc/X11/xorg.conf.d/`
  -
        Section "InputClass"
                Identifier "libinput touchpad catchall"
                MatchIsTouchpad "on"
                MatchDevicePath "/dev/input/event*"
                Driver "libinput"
                Option "ScrollPixelDistance" "50"
        EndSection
- With a name such as
  - `39-libinput.conf`
- Find similar examples in
  - `/usr/share/X11/xorg.conf.d`
