# Beautiful Minds — Exhibition Plan

An immersive, mostly visual exhibition at the intersection of science and art. Each piece communicates one beautiful idea intuitively, lets visitors interact with it, and honours the mind behind it.

## Principles

- **Touch first, read later.** A visitor should grasp the idea within ~5 seconds of interacting. Text, equations and bios are an optional second layer (small wall text, QR code to go deeper).
- **Hidden portraits.** Each piece contains a portrait of its mind, rendered in the piece's own language — Fourier drawn by epicycles, Turing grown from reaction-diffusion, Mandelbrot made of fractal detail.
- **Shared experiences.** Where possible, pieces react to several visitors at once.

## The journey

### Room 1 — Flow
| Mind | Piece | Interaction |
|---|---|---|
| Navier & Stokes | Fluid wall | Hands push ink-like fluid; hand speed sets the force |
| von Kármán | Vortex street | Your silhouette is the obstacle; walk faster to trigger turbulence |
| Kolmogorov | Turbulence cascade | Zoom across scales as eddies break into smaller eddies |

### Room 2 — Chaos
| Mind | Piece | Interaction |
|---|---|---|
| Lorenz | Butterfly effect | Two visitors launch near-identical trajectories that diverge |
| Poincaré | Three-body problem | Throw three stars; find the rare stable figure-eight |

### Room 3 — Pattern & Life
| Mind | Piece | Interaction |
|---|---|---|
| Turing | Morphogenesis | Touch to seed reaction-diffusion; knobs move through pattern space |
| Sophie Germain & Chladni | Vibrating sand plate | Sing or hum into a mic to form standing-wave patterns |
| Fibonacci | Phyllotaxis | Dial the seed angle; a perfect sunflower appears at 137.5° |
| Conway | Game of Life | Your shadow seeds living cells |
| Ramón y Cajal | Living neurons | His drawings come alive; movement makes neurons fire and grow |

### Room 4 — Infinity
| Mind | Piece | Interaction |
|---|---|---|
| Mandelbrot & Julia | Floor and wall | Your position on the Mandelbrot floor sets the Julia set on the wall |
| Penrose | Aperiodic floor | Tiles light up as you walk; the pattern never repeats |
| Escher, Poincaré, Lobachevsky | Hyperbolic space | Walk inside a Poincaré disk; the edge is never reached |
| Fourier | Epicycles | Draw a shape (or speak) and spinning circles reconstruct it |

### Room 5 — Space, Time & Light
| Mind | Piece | Interaction |
|---|---|---|
| Einstein | Curved spacetime | Visitors are masses that gravitationally lens a live camera feed |
| Huygens & Young | Ripple tank | Fingers are wave sources; two make interference fringes |
| Maxwell | Fields and light | Move a charge and watch its field ripple outward |
| Boltzmann | Entropy | Try to unmix a gas — the arrow of time made physical |

## Technology

- **Rendering:** GPU simulations (WebGL/WebGPU shaders; TouchDesigner or Unity for installations), shown on projectors or LED walls.
- **Input:** depth cameras (e.g. Orbbec) or webcams with MediaPipe pose tracking, microphones, and a few physical controls.
- **Prototyping:** every piece starts as a full-screen browser sketch with mouse/webcam input. This repo holds one sketch per mind.

## Next steps

1. Prototype three pieces first: **fluid wall**, **Mandelbrot/Julia floor**, **Turing patterns**.
2. Test them with people and refine the "5-second" interaction.
3. Write short bios and wall texts for each mind.
4. Scout venue, hardware and budget.
