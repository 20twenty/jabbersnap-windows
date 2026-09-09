# Jabbersnap Lite privacy policy

Effective September 9, 2026. This policy covers Jabbersnap Lite for
Windows. The Mac app and the remote are covered by the
[Jabbersnap privacy policy](https://github.com/20twenty/jabbersnap-mac/blob/main/PRIVACY.md).

## The short version

What you say goes to Groq, under your own API key, to be turned into text.
The text goes to your clipboard and into the app you were typing in.
Nothing else leaves your PC, and nothing is sent to us.

## What leaves your PC

- **Recordings.** When you stop a recording, its audio is sent directly
  from your PC to Groq (Groq, Inc.) for transcription, under the API key
  you put in the settings file. Groq's handling of that audio is governed
  by [Groq's privacy policy](https://groq.com/privacy-policy/).
- **Nothing else.** The program has no usage statistics, no crash
  reporting, and no server of its own. Firmware for the remote is built
  into the program; it downloads nothing.

## What stays on your PC

Two files sit next to the program, and nothing is written anywhere else:

- `jabbersnap-lite.json`: your Groq API key and settings, in plain text.
  Anyone who can read that folder can read the key.
- `jabbersnap-lite.log`: what the program printed, including the first
  line (up to 120 characters) of each transcript. Delete it whenever you
  like; a new one starts on the next run.

Audio is held in memory only while it is being transcribed and is not
saved. The remote's pairing is kept by Windows like any other Bluetooth
device.

## Removing everything

Delete the program's folder, and remove "Jabbersnap" from Settings ›
Bluetooth.

## Questions

Open an [issue](../../issues) in this repository.

## Changes

This policy is updated in place. This repository's history shows every
previous version.
