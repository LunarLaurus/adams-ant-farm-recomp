# Adam's Ant Farm

A native PC port of **Body Harvest** (Nintendo 64, 1998). It is built from the community decompilation of the game and statically
recompiled with N64Recomp, for 64-bit Windows and Linux. The US release and the European (PAL) release both run.

> **Beta.** The game is playable from start to finish with real audio, but it is not finished and you will find rough edges. That is
> what the beta is for: please tell me what you find (see [Reporting problems](#reporting-problems)).

**No game data is included, in any form.** You need your own dump of the game:

| Release | SHA-1 of the ROM |
|---|---|
| USA | `bbb6666f5014a473747ee4145f036d9fb25d7348` |
| Europe (PAL), a preview | `67750e2e7ab46fedf65a271ab7f4c7aad92ae355` |

The launcher tells the two apart from the file and starts the matching game. The package contains no copy of the ROM: you point the
launcher at your own file.

## Download

Take the newest build from the [Releases page](../../releases): a Windows zip or a Linux tarball. `SHA256SUMS` lists the checksum
of each file. Releases are marked pre-release while the version is below 1.0, so GitHub's "latest" shortcut does not point at them.

## Run it

**Windows (64-bit).** Unzip anywhere and run `bh-launcher.exe`. The package holds no DLL: on first run the launcher downloads
`SDL2.dll` into `libs/`, checking it against a pinned SHA-256 before it is used. You need the *Microsoft Visual C++ Redistributable
(x64) 2015-2022*. The programs are **unsigned**, so Windows SmartScreen may warn the first time.

**Linux (x86-64).** Unpack and run `./bh-launcher`. You need SDL2, libcurl (`libcurl.so.4`) and GTK 3 from your distribution.

Then choose your ROM in the launcher and press **Play**. A graphics card with Vulkan support is needed; on Windows you can switch the
graphics API to Direct3D 12 in the launcher if the game will not start (its two extra files are downloaded when you do).

## What it adds

- **Picture:** widescreen with the HUD anchored to the screen edges, resolution scaling, MSAA, supersampling, N64 three-point
  filtering, a high-colour framebuffer, and adjustable draw, fog and camera distance, live.
- **Textures:** texture packs, and offline extraction and upscaling of the game's own textures.
- **Input:** keyboard, mouse and controller together, with every action rebindable per pad in the launcher's **Controls** window and the
  pad's own button pictures shown.
- **In game:** a **Settings** icon in both pause menus, in the game's own style, changes the options while you play.
- **Audio:** the game's own sound microcode, recompiled rather than imitated.

Defaults reproduce the original game, so an untouched install plays like the console.

## Reporting problems

1. In the launcher open the **Session** window and choose **write a bug report**. It collects the log and settings and removes personal
   paths.
2. Open an [issue](../../issues/new/choose) with the **Bug report** form and attach that file. Say which game (US or PAL), your
   operating system and your graphics card.

Questions, ideas and "how do I...?" go in [Discussions](../../discussions). Please never attach a ROM or anything extracted from one.

## Known limits

- The PAL version is a preview; the release notes list the gaps that are known.
- This is a pre-1.0 build, so its debug tools (F8) are still in the game.

## Licence

The original code here is under the **Apache-2.0** licence ([LICENSE](LICENSE), [NOTICE](NOTICE)). The program you download links
N64ModernRuntime, so **a built program is a combined work under the GPL-3.0**; every release carries the licence texts and a
`SOURCE.txt` that names the release's **source archive** (`adams-ant-farm-source-<version>.tar.gz`, an asset of the same release).
[THIRD_PARTY.md](THIRD_PARTY.md) lists every dependency and its licence, and [NOTICES.md](NOTICES.md) the attributions.

The decompilation this is built on has no public licence of its own. It was produced collaboratively by me and Jay (jaytheham), who has
given me permission to use and distribute his contributions as part of this project; that permission is specific to this project and is
not a general licence. **Read [LEGAL.md](LEGAL.md) before redistributing anything.**
This project is not affiliated with Nintendo, Argonaut Software or the original game's rights holders.

## Credits

Built on [jaytheham's Body Harvest decompilation](https://github.com/jaytheham/body-harvest-decompilation),
[N64Recomp](https://github.com/N64Recomp/N64Recomp), [N64ModernRuntime](https://github.com/N64Recomp/N64ModernRuntime) and
[RT64](https://github.com/rt64/rt64). Two earlier Body Harvest ports informed this one:
[Body Harvest: Recompiled](https://github.com/danielgomesvieira2000/body-harvest-recomp) and
[BodyHarvest-PC-Port](https://github.com/12feihu/BodyHarvest-PC-Port).
