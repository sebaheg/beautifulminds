# Mandelbrot & Julia — "Floor and wall"

The floor is the Mandelbrot set, a map of every number *c*. Where you stand picks one
*c*, and the wall shows its Julia set: every starting point *z* that never flies away
under the rule **z ↦ z² + c**.

Step across the edge of the black shape and the wall changes character. By Fatou and
Julia's theorem, a *c* inside the Mandelbrot set gives a Julia set that is one connected
piece, and a *c* outside gives one that shatters into dust. The marker turns gold or
blue to show which side you are on, and the matching line of the theorem lights up.

The best Julia sets live right on the edge, at scales a body can't hit. So the floor
**dives**: stand still and it zooms in around your feet, which gives your steps finer
and finer control. Move quickly and it rises back out. The gold trail is the orbit of
0, the sequence the floor actually tests: it stays bounded inside the set and gets
flung away outside it.

Both views are escape-time renders on the GPU (WebGL2), using smooth iteration counts
and distance-estimate shading so the thin filaments glow.

## Run

```sh
python3 -m http.server 8765
# open http://localhost:8765/mandelbrot/ and allow the camera
```

The camera only works from `localhost` or `https`, not by opening the file directly.

**Input modes:** press `m` to cycle, or start in one with `?input=camera`:

| Mode | What drives *c* |
|---|---|
| `none` | nothing; *c* drifts on its own (a screensaver for the wall) |
| `camera` | only your silhouette; the mouse is ignored |
| `mouse` | only the mouse over the floor (the scroll wheel zooms); the camera is off |
| `both` | the default: the camera, with a moving mouse taking over for a few seconds |

The camera only runs in `camera` and `both` and switches off (light included) in the
other modes. If it can't start, `camera` mode says so instead of quietly switching to the
mouse. After a while with nobody around, *c* walks slowly around the main cardioid, stepping in
and out of the set.

**Two projectors:** open `?view=floor` and `?view=wall` in two windows on the same
machine. The floor window owns the camera and sends *c* to the wall.

**Deep links:** `?c=-0.7453,0.1127&s=0.004` jumps to a spot (`s` = half the floor height
in complex units). A few good ones:

| Spot | Link |
|---|---|
| Seahorse valley | `?c=-0.7453,0.1127&s=0.004` |
| Dendrite (floor and wall look alike) | `?c=-0.10109636,0.95628651&s=0.0005` |
| Just past the cusp: dust | `?c=0.285,0.01` |

## Keys

| Key | Action |
|---|---|
| `1` `2` `3` | layout: floor + wall · floor only · wall only |
| `z` | auto-dive on / off |
| `r` | back to the full view |
| `o` | show / hide the orbit of 0 |
| `t` | track the top of the silhouette (raised hand) ↔ its centre (overhead camera) |
| `s` | supersampling on / off |
| `f` | fullscreen |
| `v` | show the camera feed faintly (for alignment) |
| `h` | hide the text |
| `i` | invert the silhouette mask |
| `m` | input mode: none → camera → mouse → both |

Tuning lives in `CFG` at the top of the script. In the console, `mandelbrot.state()`
prints the current state, and `mandelbrot.go(x, y, s)` jumps to a spot.

## Ideas / next

- On a real floor, use an overhead depth camera with `track: 'centroid'`, and give each
  visitor their own *c*, splitting the wall into panels.
- Zoom depth is limited by float32 (about 50,000×). Perturbation theory, or emulated
  double precision, would allow endless dives.
- Hidden portrait: hide Mandelbrot's face in the colouring of a minibrot deep in
  seahorse valley.
- Tan Lei's theorem: zoom the wall around the same spot as the floor, so the two
  visibly become the same picture.
