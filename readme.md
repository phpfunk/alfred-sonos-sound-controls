## Sonos Sound Controls

The desktop app for OS X is great it almost works with all the media keys, almost. You cannot control you volume. With a speaker my office I find it be a time suck to have to tab thru the apps, find Sonos and then manually drag the sound slider. So instead enter [Alfred]((http://alfredapp.com/).

I was able to map hotkeys (Command+0, Command+- and Command+=) for mute, volume down and volume up. While not perfect it does the job.

You will need [Alfred 2 and a powerpack license](http://www.alfredapp.com/powerpack/) in order to use this. The applescript is below if you don't have Alfred and feel like using it anyway.

Also when you first use this script your system will prompt you to allow Alfred to use accessiblity controls. The reason for this is because the only want to accomplish this is to fake button clicks and volume sliders using accessbility controls. Sonos has no Applescript library for their desktop application at the moment.

To download just grab the last release [here](https://github.com/phpfunk/alfred-sonos-sound-controls/archive/master.zip).

### Versions
[See Releases](https://github.com/phpfunk/alfred-sonos-sound-controls/releases)

### Mute
```applescript
tell application "System Events"
    tell process "Sonos"
        click button 1 of window 1
    end tell
end tell
```

### Volume Down
```applescript
tell application "System Events"
    tell process "Sonos"
        set value of slider 1 of window 1 to get (value of slider 1 of window 1) - 2
    end tell
end tell
```

### Volume Up
```applescript
 tell application "System Events"
    tell process "Sonos"
        set value of slider 1 of window 1 to get (value of slider 1 of window 1) + 2
    end tell
end tell
```