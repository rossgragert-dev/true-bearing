# True Bearing v0.1 — First Wind (prototype)

Open `index.html` in a WebGL-enabled browser. No package dependencies or network access required. If a mobile file preview does not run JavaScript, serve this directory over HTTPS or use a desktop browser. For local development: `python -m http.server 8000` and open http://localhost:8000.

## Controls
- Set sail: begin simulation. Left joystick steers in helm mode; drag the view to look. Desktop: WASD/arrows, E to toggle helm, mouse drag to look.
- Leave helm: walk on the moving deck. Return near the cockpit to engage helm again.
- Auto trim toggles automatic/manual sheet control; Tack turns toward the opposite close-hauled heading.
- Menu: wind speed, waves, reefing, camera stabilization, heading hold, auxiliary engine, anchor, restart.
- Chart: three practice buoys; pass within 12 m of each in order. Chart and menu pause simulation.

## Implementation
Self-contained WebGL 1 and JavaScript (Three.js package unavailable in environment). Procedural geometry; no external assets. Fixed-step simplified polar-based simulation with apparent wind, leeway, acceleration, heel and heading hold. It is not a validated maritime training tool. Deck collision is a simplified hull boundary; cabin interior, hands, physical ropes, weather fronts, saves, races, careers and ports not implemented. No audio. Visual quality and real-device performance still require testing.

## Tests
`node physics-test.cjs` runs nine checks directly against the shipped HTML. `python test.py` attempts a Playwright Chromium browser smoke test (requires Chromium, Playwright and WebGL). See test-results.txt for actual results. Browser tests were blocked by unavailable WebGL in the execution environment.

## Research
See research/ for verbatim user prompts visible in this conversation and a development record. No GitHub repository was created and no runtime was publicly published.