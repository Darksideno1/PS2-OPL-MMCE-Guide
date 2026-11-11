# 05 — Install and first boot of RiptOPL

**Status:** general first-boot procedure, based on the RiptOPL project docs. Exact entry point on your console needs a verified boot method.

RiptOPL is a loader application, **not** a replacement for the exploit or launcher needed to execute homebrew. FMCB and FHDB are still documented entry points, alongside other methods that can start an ELF.

## Download the correct package

1. Open [RiptOPL Releases](https://github.com/NathanNeurotic/RiptOPL/releases).
2. Choose a full install kit for one edition: **Korium**, **IncebtIon**, or **RetroAchievements**. These are rolling development builds; check the release notes.
3. Download an **install kit** such as `RIPTOPL-Korium-<version>.zip`; do not accidentally choose a source snapshot or standalone variant for an initial install.
4. Record the release version, build manifest and checksum, if provided.
5. Extract the ZIP on the computer.

## Prepare and boot the loader

1. Use a working homebrew ELF launcher already installed or otherwise available on your PS2.
2. The ready application folder in the kit is `APPS/APP_RIPTOPL/`; its main executable is `RIPTOPL.ELF`.
3. Copy the folder to a storage location readable by your launcher, or use the release's compatible PSU package with an appropriate save manager.
4. Configure your launcher to start the executable at its **actual path**.
5. Boot RiptOPL and first confirm the settings menu works. Do **not** modify the HDD until you have an independent backup and have verified its layout.
6. Enable only the game source(s) you actually use under **Settings → Game Sources** and save.

The install kit may include companion `neutrino/`, `POPS/` and `EMBER/` folders. These matter for their corresponding loader cores or PS1 features; a standalone ELF update does **not** replace those companions. Do not copy proprietary BIOS files into public projects.

## Updating and rollback

- Back up your current loader, `settings_riptopl.cfg`, support files and VMCs first.
- Keep the previous working build and a note of its exact version.
- For changes to companion cores/modules, use the full installation kit, not just an ELF update.
- If a rolling build fails on hardware, restore the previously verified setup and file an issue with details.

References: [Install & First Boot](https://nathanneurotic.github.io/RiptOPL/install.html) · [Release packages](https://nathanneurotic.github.io/RiptOPL/releases.html)
