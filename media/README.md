# Screenshots

These are screenshots of the port running, used by the [project README](../README.md). They show what the program does, in three looks. They
are not extracted game data and nothing is built or run from them: see [LEGAL.md](../LEGAL.md), which says what they are and that the rights in
what they depict remain with their owners.

## The three looks

Every scene is taken the same way under each look, so the pictures can be compared.

| Look | Window | What is set |
|---|---|---|
| **vanilla** | 640x480 (4:3) | Nothing changed: the game as the console drew it. |
| **wide169** | 1920x1080 (16:9) | Widescreen on, and the picture and distance settings turned up (below). |
| **wide219** | 1920x810 (about 21:9) | The same settings, in an ultrawide window. |

The turned-up settings are every one an option in the launcher or the in-game menu, not a hidden switch:

| Setting | Value | Default |
|---|---|---|
| `BH_WIDESCREEN` | 1 | 0 |
| `BH_MSAA` | 4 | 0 |
| `BH_RES_SCALE` | 2 | 1 |
| `BH_HIGHCOLOR` | 1 | 0 |
| `BH_UPSCALE2D` | all | off |
| `BH_DRAW_DISTANCE` | 200 | 100 |
| `BH_FOG_DISTANCE` | 200 | 100 |
| `BH_FAR_PLANE` | 12000 | 6000 |

The last three are a 100 percent boost to how far entities, fog and the camera reach, which is why the wide pictures show more of the world
as well as more of the sides.

## What is here

| File | Scene | Look |
|---|---|---|
| `vanilla-comet.jpg`, `wide169-comet.jpg`, `wide219-comet.jpg` | The Comet, in the hover craft | all three |
| `vanilla-america.jpg`, `wide169-america.jpg`, `wide219-america.jpg` | America, a street | all three |
| `vanilla-greece-west.jpg`, `wide169-greece-west.jpg` | Greece, from the start looking west | vanilla and 16:9 |
| `wide169-java.jpg` | Java | 16:9 |
| `wide169-siberia.jpg` | Siberia | 16:9 |

## The icon

`icon.png` is the program's icon at 512 pixels (the same picture as `assets/icon.png`, which is compiled into the executables), kept here so
a launcher or a list that wants a URL for the project's icon can use the public repository's own copy. It is not a screenshot and shows no game
data; it is the project's own picture.

## Making more

`python tools/capture_media.py capture OUTDIR` runs the built game once per look and takes the same eight scenes (Greece at four headings, then
each later era). It needs the built game (`BH_RT64_BIN`) and your own copy of the game (`BH_US_ROM`), and it refuses a look whose window is bigger
than the display, because a window larger than the screen is clamped and the picture comes back with white bars. Choose frames that show
something, then `python tools/capture_media.py convert OUTDIR/wide169_comet.png media/wide169-comet.jpg` writes a JPEG at most 1600 pixels wide
with no metadata.

## Rules for this folder

- Only this README, JPEG or PNG screenshots, and the one icon (`icon.png`).
- Each file under 800 KB and the folder under 12 MB, with no EXIF block and no PNG text chunk. `tools/public_release.py` checks it, and refuses to
  sync a folder that breaks it.
- Name a screenshot `look-scene.jpg`, in lower case with hyphens.
- A screenshot shown in the README must be in this folder; a test fails otherwise.
- This is the only place pictures of the game are kept. A capture used for testing stays out of version control.
