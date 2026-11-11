# 07 — Internal HDD and game library

**Status:** reference / partial. Formatting is destructive; verify every drive identifier and maintain backups before doing anything.

## Which internal HDD format?

| | **APA/PFS** | **exFAT through BDM** |
| --- | --- | --- |
| Primary format | PS2 APA partitions + PFS | Standard exFAT file volume |
| Game storage | HDLoader game partitions | Game image files inside `DVD/` and `CD/` |
| Common tools | HDL-Dump and PS2 utilities | File manager on a PC |
| Capacity guidance | Up to **2 TB** in current RiptOPL docs | **GPT** for larger disks (subject to hardware and driver support) |
| RiptOPL source | HDD (APA) | Internal HDD (exFAT) + BDM devices |

**For an 8 TB disk:** the promising route documented by RiptOPL is **GPT + exFAT**, not traditional APA/PFS. But an 8 TB capacity in the docs is *not* proof that a particular SATA adapter, power setup or WD drive has been hardware-validated. Check exact disk/adapter models.

## Logical sector size is critical

RiptOPL's current disk driver requires **512-byte logical sectors**. Drives labelled **512e** (4096 physical / 512 logical) can be compatible. Native **4Kn** (4096 logical) drives are **not** supported. Check the disk's reported logical size; do not infer it only from the capacity or vendor name.

## New, empty internal HDD: GPT + exFAT outline

**Only if this is an intentionally empty disk and all needed data is backed up:**

1. Connect the disk to a computer using a compatible SATA connection/adapter.
2. Positively identify the disk by its **model, capacity and physical disk number**.
3. Confirm the drive exposes **512-byte logical sectors**.
4. For capacities over 2 TB, use a **GPT** partition table and a main **exFAT** volume, choosing the formatter's **Default** allocation unit size.
5. At the volume root, create `DVD/` and `CD/`; optionally `ART/`, `CFG/`, `VMC/`, `THM/`, `APPS/`.
6. Copy one known-good, legally obtained PS2 game image to the appropriate folder and safely disconnect the disk.
7. Install it in the PS2 and open **Settings → Game Sources**; turn on **Internal HDD (exFAT)** and set **BDM Devices Start Mode** to Manual or Auto. Save settings.
8. Check that the HDD list appears and test that single game before copying the entire library.

Never run the above format steps on an APA game disk you want to preserve. A Windows prompt to **initialize** an existing PS2 disk is not confirmation that it is blank.

## Game file layout for exFAT

```
HDD ROOT/
  DVD/
    Example-DVD-Game.iso
  CD/
    Example-CD-Game.iso
  ART/
  CFG/
  VMC/
  APPS/
```

This is a **layout illustration only**; actual filename rules, game IDs and game compatibility depend on the source/core. RiptOPL also supports ZSO where specified by its official documentation.

## Avoid fragmentation problems

Sequential file copies to a clean disk can help reduce fragmentation. The native loader has a bounded fragment table and virtual memory card files may have stricter contiguous-layout requirements. Do not reformat a disk just because a game is absent from the menu—check settings, image format, paths and diagnostics first.

## APA workflow (existing smaller drives)

If you already have a working APA/PFS library, **keep it** unless there is a deliberate migration plan. RiptOPL uses HDLoader game partitions and can work with HDL-Dump over its NBD server. This is a different workflow from dragging ISO files into `DVD/`.

References: [RiptOPL Internal HDD (APA & exFAT)](https://nathanneurotic.github.io/RiptOPL/hdd.html) · [RiptOPL Getting Started](https://nathanneurotic.github.io/RiptOPL/getting-started.html)
