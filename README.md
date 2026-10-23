# ECLIPSE

A real-time total solar eclipse for the browser. The pointer is a gravitational body.

The black disc never moves. Around it, a corona of light strands, dust and diffuse plasma responds to the hand: move to attract, press and hold to intensify, release and the light recoils. Scroll, or drag the rail on the right, through seven phases:

01 Absence · 02 Revelation · 03 Alignment · 04 Attraction · 05 Threshold · 06 Absorption · 07 Dark sun

Three colours: white, red, blue.

## Run

Open `index.html` in a browser with WebGL 2. No build step, no dependencies.

To publish with GitHub Pages: Settings → Pages → Deploy from branch → `main` / root.

## Controls

| Input | Effect |
| --- | --- |
| Move | Attract the corona |
| Press and hold | Intensify the pull (builds over ~3 s) |
| Scroll / drag the rail | Travel through the phases |
| 1–7 | Jump to a phase |
| Touch: drag / hold still | Scroll / pull |

## Files

- `index.html`: the standalone piece.
- `design/Main.dc.html`, `design/canvas.json`: the source as authored on the Claude Design canvas.

## Technique

WebGL 2, no libraries. A procedural corona shader (simplex-noise striations, helmet streamers, prominences, chromospheric rim, gravitational lens), about 3,000 spring-simulated strands and 22,000 dust particles integrated on the CPU, multisampled additive rendering, a restrained bloom, and a final plate pass that maps light to colour or ink on paper. Quality steps down automatically on slower devices; `prefers-reduced-motion` is respected.
