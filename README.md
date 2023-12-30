# TF1.Audio.English
English audio from Titanfall in **OGG** format for TFORevive.

Reduced in size by 94.1%, from 13.58GB (Titanfall 1, WAV) to 806MB (TF1.Audio.English, OGG) with no loss in quality!

Since Titanfall Online uses OGG files for all of its existing audio, I decided to export the English audio from Titanfall in the OGG format to get the benefits of a compressed audio format.

## How is this possible?
While developing [Harmony VPK Tool](https://github.com/harmonytf/HarmonyVPKTool) I noticed that prior to running the Audio Installer (`Titanfall\bin\x64\audio_installer.exe`) the audio files are stored in the OGG Vorbis format (at a bitrate of 160kbps), rather than WAV Riff (44.1KHz 24-bit PCM). Through this discovery we found that Respawn/EA shipped the desktop version of Titanfall 1 with OGG audio files to reduce the download size then converted the files to WAV during the installation process.

These files were extracted prior to the Audio Installer being run, exactly how they were as they were downloaded from Steam. This means that the audio is the same if not higher quality than the WAV files used by the game. Since the audio is converted from the OGG format, which uses lossy compression, into the WAV format which is uncompressed, these files are as small as possible while not sacrificing any audio quality.

## Why did Respawn decompress the audio in the first place?
The decision to do this was a strange one as the Titanfall branch of the Source engine supported OGG audio and even lower end hardware at the time of release could play compressed audio files (MP3, OGG, etc.) with minimal processor utilisation (and Titanfall is not a very CPU-heavy game, with game logic being processed almost entirely server-side).

It's likely they believed users would prefer the audio be in the WAV format, for less CPU usage at the expense of more storage use, or maybe they simply overlooked the fact that converting the files back to WAV from OGG would not restore them to their original quality.

It could, however, be the case that there was some unknown, issue with 160kbps OGG audio in the engine. Without fully reverse engineering the [ACACHE](https://github.com/barnabwhy/TFVPKTool/blob/main/src/acache.ts) file format used in the game it may not be possible to tell if the OGG audio would have worked out of the box.

----

### Extracted from a Titanfall game installation using scripts
Scripts utilising the [TFVPKTool](https://github.com/barnabwhy/TFVPKTool) backend were used to extract the audio from the VPK files in the Titanfall game installation.

----

### Twitter post made by p0358 following our initial discovery:
https://twitter.com/p0358/status/1545216883472977922
