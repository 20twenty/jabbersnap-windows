# Jabbersnap Lite for Windows

A small program for using a Jabbersnap remote on a Windows PC: press the
button, talk, and the words are pasted where you were typing. It also gives
the remote's other buttons a fixed set of shortcuts. It is a companion for
people trying Jabbersnap without a Mac, not the full Mac app: there is no
settings window, no voice commands, and nothing is captured or kept.

The Mac app, and everything about Jabbersnap itself, lives at
**[jabbersnap.com](https://jabbersnap.com)** and
[20twenty/jabbersnap-mac](https://github.com/20twenty/jabbersnap-mac).

- [What you need](#what-you-need)
- [Installing](#installing)
- [Using it](#using-it)
- [Settings](#settings)
- [Updating](#updating)
- [When something goes wrong](#when-something-goes-wrong)
- [Removing it](#removing-it)
- [Privacy](#privacy)

## What you need

- **Windows 10 (version 1709 or later) or Windows 11**, 64-bit.
- **A Bluetooth 5 adapter.** Most PCs' built-in Bluetooth connects but
  drops the audio. Any Bluetooth 5 USB dongle works (the TP-Link UB500,
  for example); plug it in and disable the built-in adapter in Device
  Manager. The program checks the adapter before it starts and tells you
  if the one it found is too old.
- **A Groq API key**, from [console.groq.com](https://console.groq.com).
  Transcription runs on Groq's Whisper service under your own key; the
  free tier is plenty.
- **A Jabbersnap remote** that has not been paired with another computer.
  If it has (it lived on a Mac, or on this PC with a different adapter),
  reset it first: hold buttons 2 and 6 together for five seconds, until
  the amber light blinks.

## Installing

1. Download `JabbersnapLite-<version>.exe` from the
   [latest release](../../releases/latest) into a folder of its own, for
   example `Documents\Jabbersnap`. Everything it keeps stays in that folder.
2. Run it once. Windows will say **"Windows protected your PC"** because
   the program is not yet signed: click **More info**, then **Run anyway**.
   This first run creates `jabbersnap-lite.json` next to the program and
   quits.
3. Open `jabbersnap-lite.json` in Notepad, paste your Groq API key between
   the quotes after `"groqApiKey"`, and save.
4. Run it again. It finds the remote (press any button if the remote's
   light is off), pairs with it (Windows may show a pairing notification),
   and may update the remote's firmware, which takes about a minute with a
   progress line in the window. Wait until it prints **Ready**.

Leave the window open while you work; minimized is fine.

## Using it

Click into the app you want to dictate into, then:

| Button | Tap | Hold |
|---|---|---|
| 1 | Start and stop recording. When you stop, the words are transcribed and pasted where your cursor is | Push to talk: record while held |
| 2 | Enter | Escape |
| 3 | Copy | Region screenshot to the clipboard (Win+Shift+S) |
| 4 | Paste | Undo |
| 5 | Switch to the next app (like Alt+Tab, once per tap) | Hard reload the page (Ctrl+Shift+R) |
| 6 | Next browser tab | Next Excel sheet |

The program prints this table when it starts. The transcript is also left
on the clipboard, so if it landed in the wrong place, paste it again.

If the remote's light is off, it is asleep. Any button wakes it, and the
program picks it up again on its own.

## Settings

All in `jabbersnap-lite.json`; restart the program after changing it.

| Key | Default | Meaning |
|---|---|---|
| `groqApiKey` | empty | Your Groq API key (or set the `GROQ_API_KEY` environment variable) |
| `model` | `whisper-large-v3-turbo` | Any Groq Whisper model; `whisper-large-v3` is slower and a little more accurate |
| `language` | `en` | The language you speak, as a two-letter code; empty lets Whisper guess |
| `pressEnterAfterPaste` | `false` | Press Enter after each paste, for chat boxes |
| `verbose` | `false` | Log every button press and remote power change |

## Updating

New versions appear on the [releases page](../../releases). Download the new
exe into the same folder, replacing the old one; your settings file is
kept. Each version carries the remote firmware that matches it, so the first
connection after an update may update the remote too. Wait for **Ready**.

## When something goes wrong

Everything the program prints is also written to `jabbersnap-lite.log` in
its folder. When reporting a problem, attach that file.

- **Nothing was pasted, but the text is on the clipboard.** The app you
  were typing into runs as administrator, and Windows does not let other
  programs type into it. Paste by hand.
- **The transcript went into the program's own window.** Click into the app
  you want to dictate into before pressing the button.
- **The remote does not connect.** Check it holds no pairing with another
  computer (reset it as described under What you need). If Windows refuses
  to pair, add it from Settings › Bluetooth › Add device (it appears as
  "Jabbersnap"), then start the program.
- **Audio comes back garbled or short.** The adapter is too old; see What
  you need. The log says how much of the recording was lost.
- **After a firmware update, Windows shows two "Jabbersnap" devices.** The
  old entry is harmless; remove it from Settings › Bluetooth if you like.

Open an [issue](../../issues/new/choose) for anything else. Issues are
public, so leave out anything personal; the log holds the first line of
each transcript, so check it before attaching.

## Removing it

Delete the folder. To forget the remote as well, remove "Jabbersnap" from
Settings › Bluetooth. Nothing is installed anywhere else.

## Privacy

[PRIVACY.md](PRIVACY.md), in short: your recordings go to Groq under your
own key, the transcript goes to your clipboard, and nothing else leaves
your PC. There are no usage statistics.
