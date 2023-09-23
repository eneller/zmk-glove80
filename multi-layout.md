Using xinput and setxkbmap utilities, you can set from terminal so that each keyboard to have a different layout.

First, using xinput -list | grep key command, you have to find the device ID of each keyboard. Here s an example (my case):

```bash
$ xinput -list | grep key
⎣ Virtual core keyboard                         id=3    [master keyboard (2)]
    ↳ Virtual core XTEST keyboard               id=5    [slave  keyboard (3)]
    ↳ Power Button                              id=6    [slave  keyboard (3)]
    ↳ Video Bus                                 id=7    [slave  keyboard (3)]
    ↳ Power Button                              id=8    [slave  keyboard (3)]
    ↳ Sleep Button                              id=9    [slave  keyboard (3)]
    ↳ 2.4GHz 2way RF Receiver                   id=10   [slave  keyboard (3)]
    ↳ HP Webcam                                 id=12   [slave  keyboard (3)]
    ↳ AT Translated Set 2 keyboard              id=13   [slave  keyboard (3)]
    ↳ HP WMI hotkeys                            id=15   [slave  keyboard (3)]
    ↳   USB Keyboard                            id=16   [slave  keyboard (3)]
    ↳   USB Keyboard                            id=17   [slave  keyboard (3)]
```

And second, using `setxkbmap -device <key_ID> -layout <layout_name>`, set the layout which you wish for each keyboard. An example (for my keyboards):

```bash
setxkbmap -device 3 -layout ro    #My master keyboard is set to Romanian layout
setxkbmap -device 10 -layout us   #The keyboard with id=10 is set to English (US) layout
setxkbmap -device 16 -layout ru   #The keyboard with i
setxkbmap -print -verbose 10
```