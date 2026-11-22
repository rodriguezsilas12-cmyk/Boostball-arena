# Boostball Arena

A procedural 3D browser vehicular-soccer prototype built with Three.js and Rapier3D. No downloaded game art or sound assets are required.

## Run locally
- Install Node.js 20+
- `npm install`
- `npm run dev`
- Open the local Vite URL in a WebGL2-capable desktop browser.

## Controls
- **WASD / Arrow keys** — drive and steer
- **Space** — jump, then directional dodge / flip
- **Shift** — boost
- **Q / E** — air roll; **I / K** pitch; **J / L** yaw
- **C** — toggle ball cam
- **R / Backspace** — reset car and ball
- **F2** — freeplay training panel
- **F3** — TAS / replay dock
- **F5 / F7** — save / load physics state (slot 1)
- Standard Gamepad API — left stick steer/throttle, south face button jump, right trigger boost

## Included
- Rapier fixed 120 Hz simulation loop, dynamic car and ball bodies, spring/damper chassis support, lateral tire grip, air control, jump/dodge, boost and ball spin curve force.
- Enclosed arena, open goal mouths, procedural goal frames, center markings, translucent stadium walls, pads and target ring.
- Ball cam / car cam, speed + boost HUD, training shots, physics modifiers, JSON training shot export/import, wireframe collision hitbox toggle, trajectory predictor.
- TAS pause, single-step, input recording and input JSON export, plus F5/F7 physics snapshots.

## Project structure
`src/physics.js` — Rapier world and rigid bodies  
`src/car.js` — car mesh and vehicle control  
`src/camera.js` — follow / ball camera  
`src/bakkesmod.js` — freeplay training tools and shot JSON  
`src/tas.js` — tick recorder and state snapshots  
`src/ui.js` — HUD, panels and keyboard bindings  
`src/main.js` — scene, render loop, stadium and integration

## Prototype notes
This is an arcade-sim starting point, not a full Rocket League clone. The suspension is four downward wheel raycasts with spring/damper support and simplified lateral tire grip rather than a full commercial-grade tire model; the arena's curved transitions are visual accents with simplified rectangular collision boundaries. The timeline records inputs but does not yet rewind and deterministically re-simulate edited frames. Boost trail/skid-mark particles and goal burst particles are planned extensions. Browser gamepad layouts vary by controller and browser.
