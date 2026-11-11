# 04 — Firmware and MMCE

**Status:** protocol and configuration reference; firmware flashing is deliberately not a one-size-fits-all walkthrough.

## What is MMCE?

**MMCE** (Memory Card Mass Storage Emulation) is a protocol that allows compatible adapters such as SD2PSX-derived hardware to expose microSD storage through a PS2 memory-card port. RiptOPL mounts a responding device as `mmce0:` or `mmce1:`.

The **PSxMemCard Gen2** is SD2PSX-derived and the manufacturer specifies the `sd2psx` variant of sd2psXtd firmware. **MX4SIO is different** and uses the BDM `massN:` path, not the MMCE mode.

## Before firmware updates

1. Identify the exact adapter model, hardware revision and currently installed firmware.
2. Back up the card's microSD content and keep a separate copy.
3. Read the firmware project's release notes and warnings for your specific revision.
4. Download the correct image **directly from its source project**, not an unsourced bundle.
5. Do not flash anything until the appropriate update and recovery procedure is confirmed.

## Enable MMCE in RiptOPL

1. Insert a compatible MMCE device with a prepared SD card.
2. Boot a working RiptOPL ELF.
3. Open **Settings → Game Sources**.
4. Change **MMCE Start Mode** from **Off** to **Auto** (or **Manual** if you prefer to mount on tab selection).
5. Save settings and check that the MMCE Games tab appears.
6. Optional: use the **MMCE Prefix Path** setting if you want OPL folders in a subfolder rather than the SD root.

A fresh RiptOPL config starts with game sources **Off**. If MMCE does not appear, confirm adapter firmware and the correct driver path; do not immediately format the card.

### Typical card game folders

```
DVD/   # DVD-format PS2 ISO/ZSO files
CD/    # CD-format PS2 ISO/ZSO files
ART/   # artwork
CFG/   # per-game settings
VMC/   # virtual memory cards
THM/   # themes
APPS/  # homebrew applications
```

Official sources: [RiptOPL MMCE](https://nathanneurotic.github.io/RiptOPL/mmce.html) · [sd2psXtd](https://github.com/sd2psXtd/firmware) · [PSxMemCard Gen2](https://github.com/gamebitfunx/PSxMemCardGen2)
