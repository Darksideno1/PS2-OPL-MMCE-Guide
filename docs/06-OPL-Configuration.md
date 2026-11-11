# 06 — Configure RiptOPL

**Status:** basic reference for current RiptOPL menus.

## Start with one source

After launching RiptOPL, go to **Settings → Game Sources**. Sources are initially Off in a fresh configuration; enable the one you are testing and **save changes**.

| Storage | Setting / note |
| --- | --- |
| MMCE | **MMCE Start Mode** → Manual or Auto; only for compatible MMCE cards |
| Internal APA/PFS | **HDD (APA) Start Mode**; games are HDLoader partitions |
| Internal GPT/exFAT | **Internal HDD (exFAT)** plus **BDM Devices Start Mode** |
| USB / MX4SIO | BDM device path; not the MMCE game source |
| SMB | Network server path; see upstream docs for protocol and credentials |

RiptOPL's main settings file is **`settings_riptopl.cfg`**. Its settings location follows the boot/config discovery rules and is not guaranteed to be `mc0:/OPL/`. It is intentionally separate from stock OPL's `conf_opl.cfg`.

## Game files and support folders

For **folder-based devices** (USB, MMCE, internal exFAT), use the storage root or configured prefix:

```
DVD/    # DVD-format PS2 ISO / ZSO
CD/     # CD-format PS2 ISO / ZSO
ART/    # cover and UI artwork
CFG/    # per-game configuration
VMC/    # virtual memory card files
THM/    # themes
CHT/    # cheat files
APPS/   # homebrew ELF apps
LNG/    # language assets
```

**APA/PFS HDD is different:** game images are installed as HDLoader partitions, not placed in `DVD/` files; support folders live in the configured OPL PFS data partition.

## Virtual memory cards and artwork

- Use per-game VMCs only after you have backed up existing save data.
- Keep the game's region/ID and the art filename mapping consistent with the current loader's documented naming scheme.
- In case of a loading or save issue, test with a single known-good disc image and disable optional features to isolate the cause.
- Before using an existing stock OPL configuration with RiptOPL, preserve the original; the main config files and some favorite formats differ.

References: [RiptOPL Getting Started](https://nathanneurotic.github.io/RiptOPL/getting-started.html) · [RiptOPL Installation](https://nathanneurotic.github.io/RiptOPL/install.html) · [RiptOPL MMCE](https://nathanneurotic.github.io/RiptOPL/mmce.html) · [RiptOPL HDD](https://nathanneurotic.github.io/RiptOPL/hdd.html)
