# Emmy Noether — "You break the symmetry"

A river of particles flows across a wrap-around universe. With nobody present the
laws are the same everywhere and at every moment, so the particles' momentum and
energy never change. Step in front of the camera and your silhouette becomes a wall
the particles bounce off:

- **Standing still** makes space uneven → momentum flows between you and the particles,
  but energy stays fixed.
- **Moving** also makes the laws change over time → energy flows too.

Whatever the particles gain or lose is booked to "you", so the dashed totals never move.

## Run

```sh
python3 -m http.server 8765
# open http://localhost:8765/noether/ and allow the camera
```

The camera only works from `localhost` or `https`, not by opening the file directly.
Without a camera it falls back to the mouse.

## Keys

| Key | Action |
|---|---|
| `c` | camera on / off — off makes space flat and symmetric again |
| `f` | fullscreen |
| `r` | reset the universe |
| `v` | show the camera feed faintly (for alignment) |
| `h` | hide the meters |
| `i` | invert the silhouette mask (if background and person are swapped) |
| `m` | toggle mouse / camera input |

Tuning lives in `CFG` at the top of the script; `noether.state()` in the console prints
the current momentum and energy bookkeeping.
