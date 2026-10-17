# Navier & Stokes — "Fluid wall"

The wall is filled with an invisible, incompressible fluid. Step in front of the camera
and move: wherever the edge of your silhouette moves, the fluid is dragged along at the
same speed and ink is released. Fast hands push hard; standing still makes you a rock
the current curls around.

The Navier–Stokes equation sits at the bottom of the wall, and its terms light up
as they become relevant:

- **f** (*pushed by you*) glows while someone is moving.
- **ν∇²u** (*friction*) follows the viscosity dial, from water to honey.
- **−∇p** (*pressure*) lights up in the pressure view.
- **(u·∇)u** (*carries itself*) lights up in the velocity and swirl views.

The solver is Stam's "stable fluids" on the GPU (WebGL2). It does semi-Lagrangian
advection, implicit viscosity, and a Jacobi pressure projection for ∇·u = 0, plus light
vorticity confinement.

## Run

```sh
python3 -m http.server 8765
# open http://localhost:8765/navier-stokes/ and allow the camera
```

The camera only works from `localhost` or `https`, not by opening the file directly.
Without a camera it falls back to mouse and multi-touch, and the pointer also works
alongside the camera. After a while with nobody around, invisible hands stir the wall
now and then.

## Keys

| Key | Action |
|---|---|
| `1`–`4` / `space` | view: ink · velocity · pressure · swirl (vorticity) |
| `[` `]` | viscosity: water ↔ honey |
| `f` | fullscreen |
| `r` | clear the fluid |
| `v` | show the camera feed faintly (for alignment) |
| `b` | toggle the faint body tint |
| `h` | hide the text |
| `i` | invert the silhouette mask |
| `m` | toggle mouse / camera input |

Tuning lives in `CFG` at the top of the script; `navierStokes.state()` in the console
prints the current input and solver state.

## Ideas / next

- Hidden portrait: let ink slowly settle into Navier's and Stokes' faces when the wall
  is left alone, then be scattered by the next visitor.
- Map the viscosity dial to a physical knob.
- Hand-speed → ink colour, so a calm wave and a fast swipe leave different trails.
