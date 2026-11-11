# 08 — Troubleshooting

**Status:** non-destructive first checks. Do not use formatting as a diagnostic shortcut.

## RiptOPL does not boot

- Does your console have a working ELF launch path independent of the loader?
- Does the selected file actually exist at the configured path (`RIPTOPL.ELF`)?
- Did you use a complete install kit, rather than accidentally extracting only source files?
- Can you still boot the previous known-good loader? If so, keep it available.

## No games listed

- Did you **enable** the corresponding source in **Settings → Game Sources** and save?
- Is it the right driver: **MMCE vs MX4SIO vs internal HDD exFAT vs APA**?
- For folder-based devices, are the images in `DVD/` and `CD/` at the root or configured prefix?
- For APA, were games installed as HDLoader partitions instead of being copied as ordinary files?
- Is the image format supported by that particular source/core?

## Internal disk missing

- Check adapter seating, power, controller interface and whether the drive is detected.
- Verify the logical sector size is **512 bytes**; 4Kn is unsupported.
- For a >2 TB exFAT drive, confirm **GPT** rather than an unsuitable small MBR layout.
- If an existing APA disk reports it is unformatted or a recoverable disk code, **stop writes** and consult the official disk-safety documentation. Do not initialize it.

## MMCE device missing

- Confirm the device actually speaks the **MMCE protocol** with correct compatible firmware.
- Try the correct slot or the **MMCE Slot = Auto** option.
- Set **MMCE Start Mode** to Manual or Auto; Off disables game source detection.
- Test with the manufacturer's default timing settings before tuning low-level options.

## Save trouble or VMC issue

- Preserve original saves and test with a separate known-good image.
- Check Game ID switching versus VMC files and whether the same virtual card is selected.
- Back up before testing any change that could replace a save image.

## For a useful bug report

Record: console model, boot method, RiptOPL edition/build, exact adapter, firmware revision, game identifier, storage filesystem and partition table, disk logical sector size, and the error text. Share logs/screenshots with sensitive info redacted.

[Official RiptOPL troubleshooting](https://nathanneurotic.github.io/RiptOPL/troubleshooting.html) · [Disk safety](https://nathanneurotic.github.io/RiptOPL/hdd.html)
