---
layout: default
title: PSP Terminology
---
# PSP Terminology

A reference for common PSP terms, chips, tools, and software.

## Hardware & Processors

- **Tachyon**: The main CPU and system-on-chip.
- **Allegrex**: The specific MIPS-based CPU core inside Tachyon.
- **COP1 (FPU)**: The floating-point coprocessor.
- **COP2 (VFPU)**: The vector floating-point coprocessor.
- **Media Engine**: A secondary CPU mainly for audio/video decoding.
- **Virtual Mobile Engine (VME)**: An audio processing unit for effects and
  decoding.
- **Baryon**: The system controller (Syscon) managing power, buttons, and USB.
- **Pommel**: A controller chip for GPIO and audio.
- **Kirk & Spock**: Security and cryptography engines. Kirk handles main
  encryption. Spock handles UMD keys.
- **Graphics Engine (GU)**: The GPU handling rendering and rasterization.
- **UMD (Universal Media Disc)**: Sony's optical disc format.
- **NAND Flash Memory**: The internal storage chips holding the firmware.

## Storage & Data

- **Flash0**: The internal partition holding core OS files.
- **Flash1**: The partition for user settings and registry.
- **Flash2**: The partition used for PSN DRM and activation data.
- **Flash3**: A mostly unused partition.
- **IdStorage**: A secure area containing unique console keys, region data, and
  MAC addresses.
- **Target ID**: A region identifier stored in IdStorage.
- **Memory Stick PRO Duo**: Sony's proprietary memory format.

## Boot Process & Security

- **IPL (Initial Program Loader)**: The bootloader that decrypts and loads the
  firmware into RAM.
- **iplloader**: The tiny ROM code that loads the IPL from NAND *or a Memory
  Stick*.
- **Modules (PRX)**: Executable (usually) system files loaded into memory.
- **Keys**: Cryptographic keys used by Kirk to decrypt files.

## Exploits & Recovery

- **JigKick Battery / Pandora Battery**: A modified battery that forces the PSP
  into service mode, loading the IPL from the Memory Stick.
- **Magic Memory Stick**: A Memory Stick loaded with a custom IPL for use with a
  Pandora battery.
- **Despertar del Cementerio (DDC)**: A custom unbricking tool and CFW installer
  running from a Magic Memory Stick.
- **Time Machine**: A tool that allows booting different firmware versions
  directly from the Memory Stick.
- **Brick**: When the NAND firmware is corrupt, preventing the PSP from booting.
- **Downgrading**: Flashing an older, more vulnerable firmware version.
- **Homebrew Enabler (HEN)**: An exploit that temporarily runs unsigned code
  without fully installing custom firmware. Ie; ChickHEN.

## Software & Formats

- **OFW (Official Firmware)**: The stock software from Sony.
- **CFW (Custom Firmware)**: Modified firmware allowing homebrew and backups.
  Examples: ME, PRO, ARK.
- **Infinity**: A (depricated) tool making LCFW permanent on newer models.
- **XMB (XrossMediaBar)**: The main menu interface.
- **VSH (Visual Shell)**: The technical name for the XMB and its underlying
  system.
- **VSH Menu**: A quick settings menu accessed on the XMB.
- **Recovery Menu**: A low-level boot menu for fixing issues or tweaking system
  settings.
- **POPS (PlayStation One Portable Station)**: The official PS1 emulator.
- **PBP**: The executable package format for PSP games and updates. Usually,
  EBOOT.PBP is the main executable.
- **PRX / SPRX**: Relocatable executable modules (plugins and system files).
- **ISO / CSO**: Backed-up UMD games. CSO is a compressed format.
- **PSAR**: An archive format often used in official firmware updates.
- **PMF**: PSP Movie Format (video).
- **PGF**: PSP Font Format.
- **RCO / QRC / RAF**: Resource container files used for XMB themes, sounds, and
  icons.
