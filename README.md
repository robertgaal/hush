# hush

A Mac terminal command that silences your computer before a video call.

Open Terminal (or iTerm, Ghostty, Warp, whatever you use), then type:

```sh
hush
```

Type `hush` again when the call ends.

It zeros macOS alert volume, pauses Spotify, Music, and other media apps, pauses [peon ping](https://github.com/PeonPing/peon-ping) if you have it, and turns off Cursor's thread-finished chime. Speaker and Zoom/Meet audio stay on, so you can still hear the other person.

Slack, Chrome, and other apps that play through the main speaker are not muted. Muting those would also mute the call.

## Support

macOS only. It talks to the system through AppleScript, so it will not run on Linux or Windows.

It is a bash script, not an app and not a zsh plugin. Drop it on your PATH and any shell can run it: zsh, bash, fish, whatever.

No Homebrew, no dependencies. [peon ping](https://github.com/PeonPing/peon-ping) is optional.

## Install

```sh
mkdir -p ~/.local/bin
curl -fsSL https://raw.githubusercontent.com/robertgaal/hush/main/bin/hush -o ~/.local/bin/hush
chmod +x ~/.local/bin/hush
```

If `hush` is not found after that, add this to `~/.zshrc` (or `~/.bashrc`) and open a new tab:

```sh
export PATH="$HOME/.local/bin:$PATH"
```

## Commands

```sh
hush          # toggle
hush on       # mute
hush off      # restore
hush status
```
