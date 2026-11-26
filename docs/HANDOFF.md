# True Bearing — Claude development entry point
## v0.4 — Beyond the Harbor

Repository: https://github.com/rossgragert-dev/true-bearing (private; use this existing repository, not the previously proposed true-bearing-web).
Start from main, recover and verify the deployed v0.3-alpha.1 runtime at https://shaded-comet-h636eyt.shipstatic.com, archive it unchanged and work on development/v04-beyond-the-harbor. Preserve previous releases. See BASELINE.md. The original handoff is separately archived under research/prompts/ai-handoffs when available; this entry point updates the repository name and baseline recovery guidance.

## Non-negotiable rules
Never delete files, folders, applications, or data from the user's computer. Do not force push, rewrite history, modify unrelated projects, expose secrets or private research, or overwrite working previews. Create new or versioned alternatives. Use original or properly licensed assets, record provenance, report failures honestly and obtain authorization before public deployment. Implement and test rather than merely plan.

## Scope and milestone sequence
1. Architecture and stability: reproduce baseline, audit coordinate systems, sailing/rigging, camera, mobile UI, walking, anchor, engine, heading hold, tutorial; separate simulation from renderer and modularize responsibly. Consider Three.js/glTF only if gameplay parity and mobile performance are preserved.
2. Meridian Reforged: detailed 26-foot Bermuda sloop (8.5 ft beam, 4.5 ft draft, approximate 2500 kg displacement, wheel and diesel), curved hull, teak, deck fittings, lifelines, winches, mast, boom, rigging, sails, lights and instruments. Dynamic sails with luffing, trim, tacks, jibes, reefing and hoisting.
3. Life Aboard: stable boat-relative movement, collision, eye height, camera sensitivity and stabilization, optional animated hands gripping actual equipment, compact explorable cabin with V-berth, galley, navigation station, lighting, storage, rest and safe return to cockpit. Autopilot continues when appropriate.
4. Azure Archipelago: improve water (layered waves, reflection, foam, wake, shallows, haze, clouds, buoyancy agreement), build Port Meridian marina/breakwaters/docks, Coral Bay, Windward Isles, Northwatch, Sapphire Reef. Initial target 5 × 5 nautical miles if feasible; long-term 30 × 30, accurate units and world streaming/LOD.
5. Navigation and harbor operations: depth/grounding, shoreline/dock collision, adjustable forward/reverse engine, anchors and moorings, realistic braking, charts, named destinations, waypoints, distance/ETA, heading and course over ground, speed, wind, depth, throttle and fuel instruments. Autopilot waypoint following only with honest sailing limitations.
6. Across the Blue: first voyage from Port Meridian to Coral Bay: weather, prepare, depart, navigate, enter bay, anchor; summary of distance, elapsed time, speed, engine use, efficiency, objectives. Dynamic weather/time, rain, fog, gusts, lights, presets and safe acceleration. Expand academy to points of sail, rigging, maneuvering, navigation, docking and heavy weather.
7. Release: only declare implemented and tested features. Preserve five camera modes and first-person default. Responsive portrait/landscape, large touch targets, no keyboard dependency, safe areas, multitouch, controls for helm/rig/chart/autopilot/engine. Graphics presets, adaptive resolution and a mobile 30 FPS / p95 33.3ms target; measure rather than assert.

## Testing and release
Unit tests for wind/rigging/momentum/waves, engine/anchor, ground/dock collisions, walking/cabin, camera/route, tutorial/mission, saves and input. Real browser tests (Playwright if available), portrait/landscape screenshots, device caveats, graphics failures. Capture actual gameplay, not generated concepts. Provide working preview or local build, code, branch/commit, changelog, screenshots, actual tests and performance, open issues, research records and next steps. Do not claim physical iPhone testing unless performed.

## Research
Archive every user prompt and AI implementation/handoff verbatim, relevant responses, decisions, errors, iterations, testing evidence, screenshots, release notes, timestamps, model where known, cycle IDs and commit references. Separate original records from summaries and AI-generated reflections from researcher-authored reflections. Keep research private. See research/INDEX.md.

## Suggested agents
Lead architecture/integration, marine simulation, vessel art, environment art, first-person mechanics, navigation/UX, QA and research documentation. Coordinate file ownership; sequential work if agents unavailable.

Start with baseline recovery and audit, then deliver small verified milestones. The ultimate goal is a first-person sailing simulator with exploration, ownership, career, racing and long-distance expeditions, not a rushed feature checklist.
