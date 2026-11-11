# PS2 Setup Guide — RiptOPL, MMCE & Internal HDD

A community-oriented, English-language guide to setting up **RiptOPL** on PlayStation 2, using **MMCE-compatible memory cards** (including PSxMemCard Gen2), and managing games on internal HDD, USB, or microSD storage.

> **Documentation status (11 November 2026):** This repository is a *work in progress*. Basic storage and backup guidance is based on the linked project documentation; the entire end-to-end installation has **not** yet been verified on the reference console. Follow the project's latest release notes before changing hardware or firmware.

## Start here

1. Check [hardware and prerequisites](docs/01-Required-Hardware.md).
2. **Back up** memory-card storage, configuration and any existing game library: [Backup & Recovery](docs/03-Backup-and-Recovery.md).
3. Identify your memory-card device and firmware: [PSxMemCard Gen2](docs/02-PSxMemCard-Gen2.md) and [MMCE](docs/04-Firmware-and-MMCE.md).
4. Choose a safe ELF launch method and [install RiptOPL](docs/05-PS2-Installation.md).
5. [Configure game sources](docs/06-OPL-Configuration.md), then [prepare storage](docs/07-HDD-and-Games.md).
6. For unexpected behavior, see [Troubleshooting](docs/08-Troubleshooting.md).

## Guide contents

| Section | Topic | Status |
| --- | --- | --- |
| [01 — Required hardware](docs/01-Required-Hardware.md) | Console, memory-card hardware, HDD and adapters | Reference / checklist |
| [02 — PSxMemCard Gen2](docs/02-PSxMemCard-Gen2.md) | SD2PSX-based card, saves and safe handling | Reference |
| [03 — Backups & recovery](docs/03-Backup-and-Recovery.md) | Backing up microSD without confusing it with firmware | Basic instructions |
| [04 — Firmware & MMCE](docs/04-Firmware-and-MMCE.md) | Device compatibility, protocol, game source | Reference / partial |
| [05 — Install RiptOPL](docs/05-PS2-Installation.md) | Editions, install kit, ELF boot requirements | Basic instructions |
| [06 — RiptOPL configuration](docs/06-OPL-Configuration.md) | Game sources, paths, settings and game assets | Basic instructions |
| [07 — HDD & games](docs/07-HDD-and-Games.md) | APA versus GPT/exFAT, 8 TB caution | Reference / partial |
| [08 — Troubleshooting](docs/08-Troubleshooting.md) | First checks, data safety and bug reports | Checklist |
| [Sources & verification](docs/09-Sources-and-Verification.md) | Primary sources, scope and test status | Maintained reference |

## What is RiptOPL?

RiptOPL is an actively developed **third-party fork** of Open PS2 Loader (OPL); it is **not** the official successor or a replacement mandated by the upstream project. It adds features and device support, but its rolling channels are development builds. The original upstream OPL continues separately.

**RiptOPL releases:** https://github.com/NathanNeurotic/RiptOPL/releases  
**RiptOPL docs:** https://nathanneurotic.github.io/RiptOPL/  
**Upstream OPL:** https://github.com/ps2homebrew/Open-PS2-Loader

### Storage options

| Storage | Typical game layout | Notes |
| --- | --- | --- |
| Internal HDD, APA/PFS | Games installed as HDLoader partitions | Mature classic setup; practical capacity limit 2 TB according to current RiptOPL docs |
| Internal HDD, GPT + exFAT | `DVD/` and `CD/` image files | Modern large-disk option; physical compatibility still must be tested |
| MMCE microSD | `DVD/` and `CD/` image files | Requires **MMCE-protocol** adapter, not just any memory-card adapter |
| USB / MX4SIO | `DVD/` and `CD/` image files | Different transport and driver than MMCE |
| SMB share | Games on a network server | Requires network hardware and appropriate server configuration |

## Reference test setup (not yet a compatibility claim)

- **Console:** Sony PlayStation 2 FAT SCPH-50004 (PAL)
- **Memory-card device:** PSxMemCard Gen2
- **Intended game storage:** internal SATA HDD
- **Disk considered:** WD Red Plus 8 TB
- **SATA network adapter and firmware build:** verify exact model / revision before the full walkthrough

The guide is intended to be useful to all PS2 owners, not just this configuration. Compatibility and screenshots will be marked **Hardware tested** only after physical testing.

## Safety and distribution

- Never publish personal memory-card backups, console-unique information or private save data to this public repository.
- Never format, initialize or repair a disk simply because RiptOPL cannot see it.
- Do not distribute commercial game ISOs, BIOS images or proprietary assets here.
- Link to upstream downloads and respect their licenses. Keep the original ZIP for rollback before a firmware update.
- `main` is for documentation. **Releases** may carry redistributable helper files if needed; **private backups belong elsewhere**.

## Contributions

See [CONTRIBUTING.md](CONTRIBUTING.md). Corrections and tested setup reports are welcome; please include hardware model, adapter revision, exact RiptOPL build and your storage format.

Last reviewed: **2026-11-11** · [Changelog](CHANGELOG.md)
