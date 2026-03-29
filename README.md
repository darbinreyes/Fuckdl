# FuckDL

Playready and Widevine DRM downloader and decrypter

## Description

FuckDL is a command-line program to download videos from Playready and Widevine DRM-protected video platforms.

## Features

- Support for multiple streaming services
- Playready and Widevine DRM decryption
- Download and decrypt protected content
- Multiple downloader support (N_m3u8DL-RE, Aria2c, saldl)
- DV+HDR support

## Dependencies

The following binaries must be available on your system. On macOS, install via Homebrew:

```bash
brew install aria2 bento4 mkvtoolnix ffmpeg libmediainfo
```

| Binary / Library | Package | Purpose |
|------------------|---------|---------|
| `aria2c` | `aria2` | Downloading segments |
| `mp4decrypt` | `bento4` | Decrypting DRM-protected tracks |
| `mkvmerge` | `mkvtoolnix` | Muxing tracks into MKV |
| `ffmpeg` / `ffprobe` | `ffmpeg` | Repackaging and stream inspection |
| `libmediainfo` | `libmediainfo` | Post-mux media info parsing |

> **Note:** `shaka-packager` (the default decrypter in the upstream config) is not available via Homebrew. The config in this fork is set to use `mp4decrypt` instead.

## Installation

```bash
poetry install
```

## Usage

```bash
poetry run fuckdl dl --help
```

### Hulu example

```bash
# Hulu uses Widevine. Requires an L1 WVD device for UHD/HDR content.
# With an L3 device, request SDR (default) to stay within L3 tier:
poetry run fuckdl dl Hulu "https://www.hulu.com/movie/<id>"
```

## Supported Services

- All4
- Amazon Prime Video
- Apple TV Plus
- AXN Player
- BBC iPlayer
- Bravia Core
- BritBox
- Crave
- Crunchyroll
- CTV
- Discovery Plus
- Disney Plus
- Filmio
- Flixole
- Google Play
- HBO Max
- Hotstar
- Hulu
- iTunes
- ITV
- Movies Anywhere
- Mubi
- MY5
- Netflix
- Now TV (IT/UK)
- Paramount Plus
- Peacock
- Plex
- Pluto TV
- Rakuten TV
- Roku
- RTL
- Skyshowtime
- Spectrum
- Stan
- TUBI
- TV Now
- TVNZ
- Videoland
- WowTV
- YouTube

## Configuration

1. Copy `fuckdl/config/fuckdl.yml` to your user config directory
2. Add your cookies to `fuckdl/cookies/[SERVICE]/[PROFILE].txt`
3. Add CDM devices to `fuckdl/devices/`
4. Configure credentials in `fuckdl.yml` for services that require them

## Changelog

### Version 1.2.0 (Latest)

#### Core Features
- ✨ **New**: DV+HDR function support
- ✨ **New**: YouTube script
- ✨ **New**: Mubi script
- ✨ **New**: Plex script
- ✨ **New**: AXN Player script
- ✨ **New**: BBC iPlayer script
- ✨ **New**: Bravia Core script
- ✨ **New**: Discovery+ script
- ✨ **New**: Filmio script
- ✨ **New**: Flixole script
- ✨ **New**: Google Play script
- ✨ **New**: RTL script
- ✨ **New**: Spectrum script
- ✨ **New**: TV Now script
- ✨ **New**: TVNZ script
- ✨ **New**: Hotstar script

#### Fixes
- 🔧 **Fixed**: Disney script
- 🔧 **Fixed**: HBO Max script
- 🔧 **Fixed**: Apple TV script
- 🔧 **Fixed**: Amazon script
- 🔧 **Fixed**: Crunchyroll script
- 🔧 **Fixed**: Disney Plus script
- 🔧 **Fixed**: Track.py issues
- 🔧 **Fixed**: API issues
- 🔧 **Fixed**: Vault issues

## Created By

**Barbie DRM**  
https://t.me/barbiedrm

## License

See LICENSE file for details.
