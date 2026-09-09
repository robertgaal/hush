# hush

Silence your Mac before a video call. Run it again when the call ends.

```sh
hush
```

It zeros alert volume, pauses Spotify, Music, and other media apps, and pauses [peon ping](https://github.com/PeonPing/peon-ping) if you have it. Speaker and Zoom/Meet audio stay on, so you can still hear the other person.

macOS only.

## Install

```sh
mkdir -p ~/.local/bin
curl -fsSL https://raw.githubusercontent.com/robertgaal/hush/main/bin/hush -o ~/.local/bin/hush
chmod +x ~/.local/bin/hush
```

`~/.local/bin` needs to be on your PATH.

## Commands

```sh
hush          # toggle
hush on
hush off
hush status
```
