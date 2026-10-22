# Jabbersnap for Windows

Jabbersnap turns spoken words into text in the app where you are working.
Use a Jabbersnap remote or your PC's microphone and keyboard. Configure
your controls, keep recordings in History, and use transforms to draft or
change text before pasting it.

**[Download the latest Windows release](https://github.com/20twenty/jabbersnap-windows/releases/latest)** ·
[Mac downloads](https://github.com/20twenty/jabbersnap-mac/releases/latest) ·
[jabbersnap.com](https://jabbersnap.com)

- [What you need](#what-you-need)
- [Installing](#installing)
- [Moving from Windows Lite](#moving-from-windows-lite)
- [Using Jabbersnap](#using-jabbersnap)
- [Updating and removing](#updating-and-removing)
- [Getting help](#getting-help)
- [Privacy](#privacy)

## What you need

- A **64-bit Windows PC**. The app is validated on Windows 11; the
  installer's minimum is Windows 10, but that OS is not part of the current
  validation. Windows on ARM is not validated.
- A **Groq API key** for transcription, from [console.groq.com](https://console.groq.com).
  Windows has no local transcription or live transcript preview yet.
- For a remote, **Bluetooth 4.2 or newer with Data Length Extension**.
  The app checks the adapter and explains if it is too old. Keyboard
  recording uses the PC's microphone and does not require a remote.
- For transforms and voice edit, an **Anthropic, Google Gemini or OpenAI
  API key**, configured under **System › Your AI**. Those features send
  relevant text and window images to the provider you choose.

The app does not require administrator access. Windows cannot let it paste
automatically into an app running as administrator; the text is left on the
clipboard for you to paste manually. Voice Commands and Statistics are not
available in ordinary installs.

## Installing

1. Download **Jabbersnap-0.8.16-Setup.exe** from the
   [latest release](https://github.com/20twenty/jabbersnap-windows/releases/latest).
2. Run the installer. It installs for your Windows account, adds a Start
   shortcut, and registers an entry in **Settings › Apps**.
3. Open **Jabbersnap** from Start. Follow setup to add your Groq key,
   choose the remote or keyboard, and make a practice recording. If using
   a remote, follow the on-screen pairing instructions and wait for any
   **Updating remote…** step to finish.

**This release is unsigned.** Windows may name an unknown publisher.

### SmartScreen: “Windows protected your PC”

For a download from this repository that you intend to run, choose
**More info → Run anyway**, if offered. A browser may also warn that the
download is uncommon. Check that the file is from this repository and
matches the release's file name. Each release includes its SHA-256 checksum.

### Smart App Control blocked the app

Smart App Control has no per-app exception. You can keep it enabled and
wait for a signed release, or choose to turn it off for your whole PC:

1. Open **Start → Windows Security**.
2. Choose **App & browser control → Smart App Control settings**.
3. Read the warning, choose **Off**, and confirm.
4. Run the installer again.

This removes an app-blocking protection for the whole PC; it is not an
exception for Jabbersnap. Microsoft Defender antivirus is a separate
protection. Re-enabling Smart App Control can block Jabbersnap again.
Recent Windows updates allow re-enabling without a reset, while older
versions may require resetting or reinstalling Windows. Follow the warning
on your PC. [Microsoft's explanation](https://support.microsoft.com/en-us/windows/security/threat-malware-protection/smart-app-control-frequently-asked-questions).

On a managed work or school PC, contact IT if policy blocks the download,
app, or settings change. These instructions do not override that policy.

## Moving from Windows Lite

The full Jabbersnap app replaces Lite; Lite receives no further updates.
Historical Lite releases remain available for reference.

1. Close Lite's console window. Remove any shortcut you added to run Lite
   at sign-in; only one app can use the remote at a time.
2. Copy your Groq key from `jabbersnap-lite.json` before deleting anything.
3. Install the full app and add that key during setup. It does not import
   Lite's settings file. A remote already paired to this PC can be adopted
   without a reset; otherwise follow the app's pairing instructions.
4. Review **Controls › Remote**. The full app has a different default
   button map: Button 2's hold is Undo, its tap pauses a tap-started
   recording, and Button 4's tap starts unassigned on Windows.
5. Once Jabbersnap works for you, delete the Lite folder.

Do not alternate between Lite and the full app: each carries its matching
remote software and can update the remote when it connects.

## Using Jabbersnap

The app runs in the notification area. If its icon is hidden, select **^**
on the taskbar. Click the icon for its menu and open Home from there.

With the default keyboard record key, **right Ctrl**, hold to talk or
double-tap to start and tap to finish. Change it under **Controls › Keyboard**.
Record with the remote's Record button while the destination app is in
front; **Controls › Remote** shows and edits its tap and hold assignments.

**History** keeps your recordings and results. **Behaviors › Transforms**
configures how your dictation is written for each app; drafts let you review
it and speak changes. **System › Your AI** manages transcription and AI keys.

## Updating and removing

Download the next installer and run it over the installed app. A running
copy closes for the update and reopens afterward; History, settings and keys
are retained. The app's update check opens the release page for you to
download; it does not install updates automatically.

Uninstall through **Settings › Apps**. Uninstalling keeps your data and keys
so reinstalling can pick up where you left off. To remove them, use
**Delete Data** under **System › General** before uninstalling. The app
starts at sign-in by default; change that under **System › General** or
Windows' Startup apps.

## Getting help

Open an [issue](https://github.com/20twenty/jabbersnap-windows/issues/new/choose)
with what happened, your Windows and Jabbersnap versions, and your remote's
software version if you use one. Get **Jabbersnap.log** from
**System › Help › View logs**. Review logs and screenshots before attaching
them: GitHub issues are public. Never post an API key.

## Privacy

Read [PRIVACY.md](PRIVACY.md). Recordings and History are stored locally;
cloud transcription sends audio to Groq under your key, and transforms and
spoken edits send the content they need to your chosen AI provider.
Optional usage statistics go to PostHog and can be disabled under
**System › General → Share anonymous usage statistics**. API keys are stored
in Windows Credential Manager.
