
# ARK-4 Custom Firmware

ARK-5 is a custom firmware (CFW) project for Sony PlayStation Portable (PSP) systems and the PSP emulator environment (ePSP) on PlayStation Vita.

It extends the original PSP firmware with kernel-level patches, unsigned code execution, plugin support, custom loading components, compatibility modules, and additional system-management tools.

**Project status:** ARK-4 has been archived. Its successor is ARK-5.

## Core Features

- Unsigned code execution through an enhanced CFW core.
- Kernel and system-module patching.
- Plugin support for PSP games, homebrew, PS1 titles, and VSH (XMB).
- Per-game plugin configuration.
- Inferno 2 ISO driver with support for multiple disc-image formats.
- Popcorn controller for launching custom PS1 images.
- Stargate anti-CFW compatibility engine.
- Custom IPL installation through cIPL.
- Recovery functionality and system restoration tools.
- Custom game launcher with additional system utilities.
- OTA update functionality in the ARK-4 release line.

## Firmware Architecture

ARK-4 uses a modular architecture in which dedicated components handle system patching, compatibility, game loading, and user-facing functionality.

### SystemControl

The central CFW component. It provides patches for unsigned code execution and exposes the API used by other ARK modules.

### VshControl

Handles patches to the PSP VSH environment (XMB), enabling homebrew and ISO launching and integrating additional firmware functionality.

### Compatibility Layer

Provides platform and software compatibility adjustments. Core compatibility modules include:

- `psp`
- `vita`
- `vitapops`
- `pentazemin`

### Stargate

Handles anti-CFW protections and selected game compatibility fixes.

### Inferno

Custom ISO driver supporting compressed and uncompressed PSP disc-image formats.

### PopCorn

Provides support for launching custom PlayStation 1 images through the PSP's Pops environment.

### XMB Control

Adds configuration functionality to the XMB, including CFW settings and plugin management.

## Loading and Boot Components

ARK-4 supports multiple loading and installation configurations.

| Component | Function |
|---|---|
| ARK Loader | Loads ARK as a live CFW |
| FinalSpeed | Provides an additional live-CFW launch method |
| Signed Loader | Specially configured EBOOT.PBP loader |
| Savedata Exploits | Legacy exploit-based loading methods |
| Classic cIPL | Custom IPL for compatible PSP hardware |
| New IPL | Updated custom IPL implementation |
| Time Machine | Supports booting firmware from Memory Stick |
| Despertar del Cementerio | Recovery and firmware installation environment |

The available method depends on the PSP model, firmware version, and existing system configuration.

## Custom IPL and Installation Types

ARK-4 offers several installation modes.

### Live CFW

ARK is loaded from the memory card and remains active until the system is powered off or restarted. The loader must be executed again after reboot.

### Standard Installation

Uses cIPL to enable permanent CFW boot functionality.

### Full Installation

Installs additional ARK components to internal flash storage. The exact feature set differs from other installation types.

### Classic and Light Installations

Alternative permanent installation configurations with different flash-storage requirements.

### Time Machine Installation

Allows ARK and supported firmware configurations to be booted from a Memory Stick.

**Important:** cIPL and flash operations modify low-level boot or system storage. The correct installation method must be selected for the exact hardware revision.

## Disc Image Support

The Inferno 2 driver supports the following documented PSP image formats:

- ISO
- CSO
- ZSO
- JSO
- CSOv2
- DAX

Driver behavior and compatibility can vary depending on the image, game, and firmware configuration.

## Plugin System

ARK-4 supports plugins in several PSP operating environments:

- PSP games
- Homebrew applications
- PS1 games
- VSH (XMB)

Plugins can be enabled or disabled globally or configured for individual games, depending on the plugin type and configuration.

## PlayStation 1 Compatibility

The PopCorn component supports custom PS1 images in the PSP Pops environment.

External configuration files can be used to apply title-specific compatibility adjustments.

On PS Vita, ARK-4 also supports ePSP-based configurations, including ARK-X for PS1-oriented use.

## Recovery and Maintenance

ARK-4 includes tools and boot options for system maintenance.

- Recovery menu for selected soft-brick and configuration problems.
- Despertar del Cementerio Version 10 integration.
- Pandora Battery and Baryon Sweeper recovery workflows.
- Boot-time options for accessing recovery environments.
- Custom IPL removal and installation options.

Recovery availability depends on hardware, boot configuration, and the type of system failure.

## Platform Compatibility

| Platform | Supported configuration |
|---|---|
| PSP | PSP firmware 6.60 and 6.61 |
| PSP Testkit / Devkit | Documented 6.60 testing and development firmware configurations |
| PS Vita | PSP ePSP environment on firmware 2.10–3.74 |
| PS Vita with Adrenaline | Supported Adrenaline-based PSP environment |

The project documentation excludes the Strider2 PSP hardware variant. Compatibility statements should be checked against the specific installation method and device configuration.

## Build Environment

The project includes a build script and Makefile-based development workflow.

The documented build process supports a Docker-based development environment.

### Build Commands

Build a release:

```bash
./build.sh
```

Build a debug version:

```bash
./build.sh --debug
```

For additional build options:

```bash
./build.sh --help
```

Manual compilation is also documented using the appropriate PSP SDK and Makefile workflow.

## Source Tree

The repository contains several primary development directories:

| Directory | Purpose |
|---|---|
| `common/` | Shared code and definitions |
| `core/` | Core custom firmware components |
| `extras/` | Additional utilities and modules |
| `libs/` | Libraries and dependencies |
| `loader/` | Loader-related components |
| `contrib/` | Supporting files and contributed resources |

The repository also includes build scripts, a Makefile, changelog, and Git submodule configuration.

## Project Status

ARK-4 is an archived project. Its final official release was published as `v4.20.69 r206`.

The project maintainers directed users toward ARK-5 as the successor.

This repository remains useful as a reference for the ARK-4 firmware architecture, source code, historical releases, and development work.

## Project Information

| Property | Value |
|---|---|
| Project | ARK-4 |
| Project type | Custom Firmware |
| Primary platform | Sony PlayStation Portable |
| Additional environment | PlayStation Vita ePSP |
| Firmware compatibility | PSP 6.60 / 6.61 |
| Main components | SystemControl, VshControl, Stargate, Inferno, PopCorn |
| Boot modification | cIPL / Custom IPL |
| Build system | Shell build script and Makefile |
| Status | Archived |
| Successor | ARK-5 |

## Official Resources

- Source repository: https://github.com/PSP-Archive/ARK-4
- Wiki: https://github.com/PSP-Archive/ARK-4/wiki
- Development documentation: https://github.com/PSP-Archive/ARK-4/wiki/Development
- Releases: https://github.com/PSP-Archive/ARK-4/releases
- Successor project: https://github.com/PSP-Arkfive/ARK-5

---

ARK-4 is a modular PSP custom firmware that combines kernel-level patching, compatibility components, custom boot support, plugin management, and recovery functionality.
