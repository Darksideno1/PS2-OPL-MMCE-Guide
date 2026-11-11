# 01 — Hardware and prerequisites

**Status:** reference / checklist; specific combinations still need physical testing.

## Minimum items

- PlayStation 2 (FAT or Slim) and a working display / controller.
- A **known working way to launch homebrew ELF files**. FMCB, FHDB, certain disc-based exploits or a supported alternative are possible. MMCE itself is *not* automatically an ELF boot exploit.
- USB, MMCE-compatible device, supported network source, or internal HDD for games.
- A Windows, Linux or macOS computer to prepare files and store backups.
- An original copy of your memory-card files or a backup before changing anything.

## Devices: do not confuse them

| Term | Meaning |
| --- | --- |
| PSxMemCard Gen2 | SD2PSX-derived memory-card solution; can expose MMCE functionality with compatible firmware |
| MMCE | Protocol to access compatible memory-card-slot storage as a block device |
| MX4SIO | A different adapter/driver route; it is **not** the MMCE protocol |
| RiptOPL | The game loader application; normally launched as an ELF |
| FMCB / FHDB | Boot methods that can launch an ELF; RiptOPL docs still describe them as usable |

## FAT PS2 + internal SATA drive

Check the network adapter's physical interface, SATA modification/clone details, power and drive clearance. Confirm the HDD reports **512-byte logical sectors (512n or 512e)**; 4Kn is not supported by current RiptOPL disk code. For disks above 2 TB, see [07 — HDD & games](07-HDD-and-Games.md) *before* initializing them.

[Source: RiptOPL getting started](https://nathanneurotic.github.io/RiptOPL/getting-started.html) · [Source: RiptOPL internal HDD](https://nathanneurotic.github.io/RiptOPL/hdd.html)
