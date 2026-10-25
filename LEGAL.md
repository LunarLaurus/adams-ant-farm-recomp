# Legal

Short version: `LICENSE` (Apache-2.0) covers this repository's own original code. It does not
grant any rights to Body Harvest itself, to any third-party dependency under different terms, or
to the decompilation this project is built on (which currently has no license at all). Read on
for what that actually means.

## Scope of the Apache-2.0 license

This license applies only to original code and other copyrightable material contributed to this
repository by the project authors. It does not grant rights to Nintendo, Argonaut Software, or
any other third party's intellectual property, including the original Body Harvest game,
trademarks, original assets, music, textures, models, or other copyrighted material.

That distinction matters more here than it would for a typical open-source tool, because this
project is a recompiled, playable port of a specific commercial game - not merely research or
decompilation tooling. Nothing in this repository's license, `NOTICE`, or any other document is
an assertion of ownership over, or a grant of rights to, Body Harvest or any of Nintendo's or
Argonaut's intellectual property in it. This project contains no game data: no ROM, no dump, no
extracted or copied assets, textures, models or audio from the original game (this project's own
hard rule - enforced throughout this codebase, not just stated here). Anyone running this project
supplies their own legally obtained copy of the game.

The one thing in this repository that shows the game's pictures is `media/`: a small number of
screenshots of this program running, scaled and stripped of metadata, which the README uses to show what
the port does. They are illustrations of the running program, not extracted game data, and the rights in
what they depict remain with their owners; this licence does not cover them. They are never used to
build or run anything.

## The decompilation this project is built on has no public license yet

`lib/bh-decomp` (jaytheham/body-harvest-decompilation), the decompiled source this entire project
is built against, currently has **no public open-source license**; its licence is upstream's to decide
and has not been decided yet. The decompilation work itself was produced collaboratively by LunarLaurus
and Jay (jaytheham), and Jay has granted LunarLaurus permission to use and distribute his
contributions as part of this project. That permission is real and specific to this project's
authors - it should not be read as a general relicensing of the upstream decompilation project or
of contributions made by other parties to it. Upstream licensing of `lib/bh-decomp` itself remains
a separate, still-open matter, and resolving it is upstream's decision, not something this repository can
settle. This describes what this repository does, not who has worked on the decompilation: no decomp
matching or verification work happens in this repo, which pins `lib/bh-decomp`'s commit and, where a real
gap blocks the port, carries a tracked patch under `patches/decomp/`. Until the decompilation itself has
a public license, treat its status as unresolved for anyone other than this project's authors - not as
implicitly permissive, and not as covered by this repository's own Apache-2.0 grant, which cannot license
code this project doesn't solely own.

## The distributed binary is a GPL-3.0 combined work

This project links [N64ModernRuntime](https://github.com/N64Recomp/N64ModernRuntime) (GPL-3.0)
directly into the built `adams-ant-farm` binary. Under GPL-3.0's own terms, this makes the
**distributed binary** a combined work bound by GPL-3.0's copyleft obligations (source
availability on request, etc.), regardless of this repository's own code being separately
licensed Apache-2.0. Apache-2.0 is one-way compatible with GPL-3.0 (Apache-2.0 code may be
included in a GPL-3.0 combined work), but that compatibility runs one direction: it does not make
the combined, distributed binary Apache-2.0, and it does not relax GPL-3.0's requirements on that
binary. If you distribute a build of this project, you are distributing a GPL-3.0 combined work,
not an Apache-2.0 one - see `THIRD_PARTY.md` for the full dependency list and each one's actual
license.

## Full third-party inventory

See `THIRD_PARTY.md` for every vendored dependency and the license it's actually under, and
`NOTICES.md` for attribution on specific code adapted from other MIT-licensed Body Harvest recomp
projects.
