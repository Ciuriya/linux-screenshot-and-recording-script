# Screenshot and Recording script for linux
I made this script as a personal replacement for my use of shareX.

# How it works
It grabs slurp output and feeds it into grim/wf-recorder to produce an output, 
which is fed directly to a file over the network using sshfs or whatever else the user has.

The resulting url is copied after the operation is successful.

Valid arguments to call the script:
- region
- record
- record-no-audio

To stop (finalize) a recording, simply call record/record-no-audio again.

# Requirements
- slurp (https://github.com/emersion/slurp)
- grim (https://github.com/emersion/grim)
- wf-recorder (https://github.com/ammen99/wf-recorder)
- some way to handle remote file transfer seamlessly, I use sshfs

# Install
Drop it wherever you'd like and call it from your preferred hotkey / script hub. I only tested with hyprland.

Make sure you go in the script and change the variables to match your paths and your needs.

IMPORTANT: Create the temp folder for the temp files to actually have somewhere to go, unless you change those paths in the script.

# Example setup in hyprland
hl.bind("CONTROL + SHIFT + R", hl.dsp.exec_cmd("sh $HOME/.config/scripts/screenshot-and-recording-handler record"), { locked = true, submap_universal = true, non_consuming = false })
