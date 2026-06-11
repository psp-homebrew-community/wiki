---
layout: default
title: Boot Process
---
# Boot Process

- **Kirk & Spock**: Security and cryptography engines. Kirk handles main encryption. Spock handles UMD keys.
- **IPL (Initial Program Loader)**: The bootloader that decrypts and loads the firmware into RAM.
- **iplloader**: The tiny ROM code that loads the IPL from NAND *or a Memory Stick*.
- **Modules (PRX)**: Executable (usually) system files loaded into memory.
- **Keys**: Cryptographic keys used by Kirk to decrypt files.
