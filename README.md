# KubaOS wallpapers

The wallpaper sets of [KubaOS](https://github.com/SuplenC/kubaos), one folder
per set:

| Set | What |
|---|---|
| [`shinjuku/`](shinjuku/CREDITS.md) | KubaOS Shinjuku's own set |
| [`japanese/`](japanese/CREDITS.md) | Tokyo at blue and purple hour |
| [`cyberpunk/`](cyberpunk/CREDITS.md) | Tokyo neon at night |

Each folder's `CREDITS.md` names the photographer, source and license of
every file in it.

## How KubaOS uses it

KubaOS takes this repository as a flake input (`flake = false`), pinned in
its own `flake.lock`. The payload ships every set read-only under
`/usr/share/kubaos/wallpapers/<set>/`, and the installer asks which sets to
use. A new set here reaches installed machines with the next KubaOS release,
and shows up once the user chooses it.

## Adding a set

A set is a folder of images (jpg, jpeg, png, webp) or videos (mp4, webm, mkv,
mov, each with a `<name>.poster.jpg` next to it) plus a `CREDITS.md`. The
folder name is the set's id: lowercase letters, digits and dashes. The
installer previews a set with its first image by name.

Stills are the photographer's original, downscaled to 3840 px wide (Lanczos)
and re-encoded as progressive JPEG, quality 90, 4:4:4 chroma, metadata
stripped. All are 3:2 (or close), so they crop cleanly to both 16:10 and 16:9.

Removing a set or a file needs care: someone may have it as their current
wallpaper.
