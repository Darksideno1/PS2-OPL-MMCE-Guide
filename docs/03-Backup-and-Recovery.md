# 03 — Backup and recovery

**Status:** basic file-backup procedure; restore details depend on device/firmware.

## Back up the PSxMemCard Gen2 microSD

1. Shut down the PlayStation 2 completely.
2. Remove the microSD card and insert it into a suitable computer card reader.
3. If Windows offers to format or repair the card unexpectedly, **cancel** and verify the correct drive/device first.
4. Show hidden files and copy **all accessible files and folders** from the card to a new folder, e.g. `PSxMemCard-Gen2-Original-2026-11-11/`.
5. Verify the source and copy contain the expected folders, files and sizes. Open a small sample to ensure the copy is readable.
6. Optionally archive the copied folder to ZIP and **test ZIP extraction** before relying on it.
7. Save a second copy offline / on a NAS. Keep an untouched original snapshot.

A file copy protects the microSD contents, **not** the device's internal firmware. If you suspect an unrecognized/complex partition layout, make an appropriate **full-card image** as well rather than assuming Explorer shows all sectors.

## Back up other PS2 data

- RiptOPL settings, per-game configs, cover art, VMC files and network configuration.
- The boot entry point and method required to get an ELF running again.
- Other memory-card saves and a separate library list / asset inventory.
- The installed app version and archive checksum/manifest when available.

RiptOPL uses its own main configuration file, **`settings_riptopl.cfg`**, not stock OPL's master `conf_opl.cfg`. Its location depends on the configured settings home; do not assume `mc0:/OPL/` in every installation.

## Restore principle

Restore only to the **correct device and folder structure**, after checking current firmware compatibility. Keep the backup source read-only until the restored device is verified. If the disk is not recognized, do not initialize or reformat it as a first troubleshooting step.

## Public repository policy

**Never upload personal memory-card backups to this public GitHub repo or its Releases.** A GitHub deletion does not guarantee that secret content disappears from cloned repositories or history.

Sources: [RiptOPL installation](https://nathanneurotic.github.io/RiptOPL/install.html) · [PSxMemCard Gen2](https://github.com/gamebitfunx/PSxMemCardGen2)
