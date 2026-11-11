# 02 — PSxMemCard Gen2

**Status:** manufacturer and firmware documentation reference; actual card firmware/PCB must be checked before updating.

PSxMemCard Gen2 is a **microSD-backed PS1/PS2 memory-card device** based on the SD2PSX architecture. The manufacturer identifies the compatible **`sd2psx` firmware variant** of the sd2psXtd project. Never flash a firmware variant for a different card model based only on a similar name.

## Before changing settings

1. Power down the console and remove the device safely.
2. Copy the full *visible and hidden* microSD contents to a folder on a computer; see [Backup & Recovery](03-Backup-and-Recovery.md).
3. Make an additional copy on another disk and check that it can be read.
4. Record the current firmware version, memory-card mode, microSD size and any boot-card configuration.
5. Keep the original untouched until the setup and save loading are verified.

**Important:** A copied microSD folder is a **file backup**, not a dump of the microcontroller firmware. For a firmware rollback, follow device-specific flashing instructions and save a verified compatible release beforehand.

## Two distinct uses

- **Memory card / saves:** the device emulates memory cards and can offer per-game save handling.
- **MMCE game storage:** compatible firmware can also expose the microSD contents to a loader that supports the MMCE protocol (such as RiptOPL). This is different from an MX4SIO adapter.

## Firmware

Use only firmware instructions for this **exact hardware revision**. Do not infer that the latest version is necessarily safer for an already working installation. Back up before flashing; do not interrupt power during a firmware update.

Sources: [PSxMemCard Gen2 manufacturer project](https://github.com/gamebitfunx/PSxMemCardGen2) · [sd2psXtd firmware](https://github.com/sd2psXtd/firmware) · [RiptOPL MMCE](https://nathanneurotic.github.io/RiptOPL/mmce.html)
