# Edit Touchpad Gestures on Pop!_OS

## Copy the default config from 
    /usr/share/touchegg/touchegg.conf
### to
    ~/.config/touchegg/touchegg.conf

## Edit these lines in config

    <gesture type="SWIPE" fingers="4" direction="RIGHT">
      <action type="RUN_COMMAND">
        <repeat>false</repeat>
        <command>dbus-send --session --dest=com.System76.Cosmic --type=method_call /com/System76/Cosmic com.System76.Cosmic.GestureLeft</command>
        <on>begin</on>
      </action>
    </gesture>

## Editing this line
    --type=method_call ... com.System76.Cosmic.GestureRight</command>
### to
    --type=method_call ... com.System76.Cosmic.GestureLeft</command>

# For more info
https://github.com/pop-os/touchegg#using-touch%C3%A9