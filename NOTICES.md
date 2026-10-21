# Notices

Code reused beyond a straight submodule pin or build dependency, with the attribution its
license requires. General credits (repos this project builds on or was informed by) are in
`README.md`'s Credits section.

## danielgomesvieira2000/body-harvest-recomp

<https://github.com/danielgomesvieira2000/body-harvest-recomp> - MIT License, Copyright (c) 2026
Body Harvest: Recompiled contributors.

- `patches/n64recomp/0003-RSPRecomp-mask-indirect-jump-low-bits.patch` ports the fix in their
  `tools/patch_rsprecomp.py`: RSPRecomp's indirect-jump dispatch switches on a raw computed
  target instead of masking it to RSP's true word-aligned 12-bit program counter, so a target
  whose low bits carry something real hardware discards falls through as an unhandled jump.

## 12feihu/BodyHarvest-PC-Port

<https://github.com/12feihu/BodyHarvest-PC-Port> - MIT License, bh-recomp-toolkit contributors.

- `patches/runtime/0002-ultramodern-dont-quick-exit-on-unresolved-rsp-exit.patch` is informed by
  their `bh-rsp/fixup_aspmain.py` finding: a recompiled microcode can reach an exit RSPRecomp
  could not resolve to a label (an indirect jump landing back in rspboot, in their case) on every
  single audio task, as the hardware's normal completion path rather than a fault. My patch
  generalises their per-case fix into runtime resilience - skip the one task instead of ending
  the process - since this build does not yet model every such address precisely enough to
  convert each one to the correct exit reason at the recompiler level.
- `rsp/aspMain.us.toml`'s `text_size = 0xF80` (the full declared DMA length, not a truncated
  guess) matches their `bh-rsp/aspMain.toml`.
