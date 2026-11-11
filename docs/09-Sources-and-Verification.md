# 09 — Primary sources and verification status

**Reviewed:** 2026-11-11. Features and releases may change; always recheck upstream before flashing or formatting.

## Primary sources

| Project | Source | Scope |
| --- | --- | --- |
| RiptOPL | https://github.com/NathanNeurotic/RiptOPL | Main fork and releases |
| RiptOPL documentation | https://nathanneurotic.github.io/RiptOPL/ | Current setup reference |
| RiptOPL install | https://nathanneurotic.github.io/RiptOPL/install.html | ELF/package install |
| RiptOPL releases | https://nathanneurotic.github.io/RiptOPL/releases.html | Rolling channels and editions |
| RiptOPL MMCE | https://nathanneurotic.github.io/RiptOPL/mmce.html | MMCE setup and start modes |
| RiptOPL HDD | https://nathanneurotic.github.io/RiptOPL/hdd.html | APA/exFAT, GPT, capacity and safety |
| Upstream OPL | https://github.com/ps2homebrew/Open-PS2-Loader | Canonical OPL project |
| PSxMemCard Gen2 | https://github.com/gamebitfunx/PSxMemCardGen2 | Device documentation |
| sd2psXtd | https://github.com/sd2psXtd/firmware | Firmware family and hardware variants |

## Verification labels

- **Documented upstream**: included in the official project references linked above.
- **Hardware tested**: verified on a specifically described physical PS2, with steps and build ID.
- **Community reported**: observed on a particular external setup; not independently reproduced here.
- **Planned / unverified**: a procedure or combination that has not yet been confirmed.

## Pending hardware verification

- SCPH-50004 PAL boot method and exact initial launcher setup.
- PSxMemCard Gen2 actual firmware revision and MMCE storage detection.
- SATA network adapter variant and compatibility.
- WD Red Plus 8 TB exact model and reported **logical** sector size.
- GPT/exFAT behavior under a specific RiptOPL build, including games, VMC and reset.

**Why this matters:** RiptOPL's rolling releases may change daily. The existence of a feature in documentation does not demonstrate compatibility with every adapter or console.
