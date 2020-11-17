# GPMDP-PlayerInfo
A Simple but modular script to pull song info from Google Play Music Desktop Player. Built with the intent of extending status bars such as i3blocks. This script assume you playback.json file is in ~/GPMDP_STORE/playback.json (which is the default)

Google Play Music Desktop Player - https://github.com/MarshallOfSound/Google-Play-Music-Desktop-Player-UNOFFICIAL-

## Usage
```
usage: playing.py [-h] [-l layout] [-t trunclen] [--not-playing]

Parses and print Google Play Music Desktop Player song info

optional arguments:
  -h, --help            show this help message and exit
  -l layout, --layout layout
                        t = Song Title
                        a = Song Album
                        A = Artist Name
                        p = Track time progess
                        - = Spacer
                        Example: t-a-A-p
  -t trunclen, --trunclen trunclen
                        Truncate the output
  --not-playing         Display the text 'Not Playing' when no music is playing
```

The `--layout` option allows you to change the order the infomation is displayed in.
Example: `player.py --layout t-a-A-p`

## i3Blocks
```ini
[music]
label=
command=<PATH-TO-SCRIPT>/gpmdp-playing/playing.py
separator_block_width=13
interval=10
color=#EEFF66
```

## Polybar
```ini
[module/music]
type = custom/script
interval = 1
;format-prefix = " "
format = "<label>"
exec = <PATH-TO-SCRIPT>/GPMDP-PlayerInfo/playing.py
format-underline = #f00
```
