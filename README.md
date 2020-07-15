Omni is intended to be a painfully simple way to build a button interface
for common shell commands on touchscreen devices, with a specific focus
on the Pinephone. 

It accepts input either from a file or STDIN, reading lines in pairs and
creating a button with the first line as the button text and the second a
command to be passed to the shell when the button is pressed.  This exact
method for input will likely be changed (or at least extended) in the
future. 

# Examples:

    Yes
    echo yes
    No
    echo no

This tells omni to create two buttons labeled "Yes" and "No", which will
echo the indicated word to the terminal.

**mediabuttons.omni**:
    Play
    ssh user@host mediaplayer --play;omni mediabuttons.omni
    Pause
    ssh user@host mediaplayer --pause;omni mediabuttons.omni
    Next
    ssh user@host mediaplayer --skip;omni mediabuttons.omni
    Exit
    sleep 0


This could be used as a remote control for a media player running on a
remote system.  Note that each command runs omni again, causing the
buttons to persist.
