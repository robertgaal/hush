# hush

A Mac terminal command that silences your computer before a video call.

Open Terminal (or iTerm, Ghostty, Warp, whatever you use), then type:

```sh
hush
```

Type `hush` again when the call ends.

## What it mutes

- macOS alert volume: system beeps, Finder sound effects, and Notification Center sounds
- Spotify, Music, TV, QuickTime, VLC, IINA, VOX, and Swinsian (paused)
- [peon ping](https://github.com/PeonPing/peon-ping), if installed
- Cursor's "chime after chat finishes" and its accessibility signals (the pings on tool calls, file edits, and finished terminal commands)

Speaker and Zoom/Meet audio stay on, so you can still hear the other person.

Cursor gets its own switch because its sounds play through the main output, not the alert channel. hush flips `cursor.composer.shouldChimeAfterChatFinishes` to `false` and `accessibility.signalOptions.volume` to `0` in Cursor's `settings.json`, then puts both back on `hush off`. Cursor picks the change up live.

The signal volume matters if you run Cursor with `editor.accessibilitySupport` set to `on`. That turns every signal left on `auto` into an audible ping, and the chime toggle doesn't cover those.

Claude Code, the Claude desktop app, and Codex CLI don't need one: their sounds go through the terminal bell, Notification Center, or peon ping, all of which the alert volume already covers.

## Support

macOS only. It talks to the system through AppleScript, so it will not run on Linux or Windows.

It is a bash script, not an app and not a zsh plugin. Drop it on your PATH and any shell can run it: zsh, bash, fish, whatever.

No Homebrew, no dependencies. peon ping and Cursor are optional.

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
