# TRUE BEARING
## v0.4-alpha.1 — Beyond the Harbor
### Autonomous Development and Implementation Handoff

You are taking over development of True Bearing, an immersive, first-person, open-world sailing simulator combining realistic sailing physics, exploration, career progression, competitive racing and vessel ownership.

Act as a senior game developer, marine simulation engineer, 3D environment artist, technical artist, UX designer and quality assurance engineer.

This is an implementation assignment, not merely a planning exercise. Audit the existing game, identify and resolve issues, implement the following upgrades, test them and produce a playable development preview.

## 1. Mandatory development rules

- Under no circumstances may you delete files, folders, applications or other data from my computer. Preserve existing files and create new or versioned alternatives when necessary.
- Never overwrite the last working release.
- Do not make unrelated changes to my computer or other projects.
- Never expose credentials, private research documents, personal information or private assets.
- Preserve all existing gameplay features unless a replacement is demonstrably better.
- Use isolated development branches and frequent, descriptive commits.
- Do not force-push or rewrite Git history.
- Do not publish private repository contents.
- Use original artwork or appropriately licensed assets. Document all external asset sources and licenses.
- Do not fabricate testing results, performance measurements or completed features.
- Work autonomously through the implementation phases without requesting approval for routine design or engineering decisions.
- Clearly document any unresolved technical limitations.

## 2. Current development baseline

Current release: **v0.3-alpha.1 — Master the Rig**

Live preview:
https://shaded-comet-h636eyt.shipstatic.com

Previous working release:
https://driven-nano-sc5h3pz.shipstatic.com

The existing game uses a custom, self-contained WebGL renderer and JavaScript simulation.

A v0.2 source archive containing earlier physics tests, rendering tests, research documentation and source files is available separately.

Recover the latest runtime source from the current live preview if the complete v0.3-alpha.1 source is not already available locally. Verify its contents before using it. Do not simply revert to v0.2 and lose subsequent features.

Existing reported features include:

- First-person helm perspective
- Walkable vessel deck
- True and apparent wind
- Wind-dependent propulsion
- Vessel momentum, drag and leeway
- Boat heel, pitch and roll
- Automatic and manual sail trimming
- Independent mainsail and jib controls
- Sail hoisting, lowering and reefing
- Interactive cockpit winches
- Tacking
- Auxiliary engine
- Anchoring
- Autopilot heading hold
- Navigation chart
- Practice buoy course
- Direction, bearing and distance indicators
- Dynamic ocean waves
- Daylight, sunset and nighttime lighting
- Environmental audio
- Sailing Academy with seven instructional stages
- Mobile portrait and landscape controls

Preserve all five camera perspectives:

1. First-person helm
2. Wide-angle helm
3. Bow
4. Masthead
5. Third-person chase

First-person must remain the primary gameplay experience. Alternative views are navigation and accessibility tools.

The previous development iteration reported 21 passing physics and rigging tests. Reproduce these tests where possible rather than assuming the reported results remain valid.

Mobile gameplay and full tutorial completion have not been independently verified.

## 3. GitHub repository and project organization

If a repository does not already exist, establish a private GitHub repository named:

`true-bearing-web`

Use my existing GitHub account when available.

Create an isolated development branch:

`development/v04-beyond-the-harbor`

Preserve the recovered baseline as a separate commit or tag.

Refactor the current monolithic HTML implementation into a maintainable modular architecture where appropriate.

Recommended organization:

- `src/core/`
- `src/physics/`
- `src/ocean/`
- `src/weather/`
- `src/vessels/`
- `src/world/`
- `src/navigation/`
- `src/player/`
- `src/interactions/`
- `src/camera/`
- `src/audio/`
- `src/ui/`
- `src/academy/`
- `src/save/`
- `assets/models/`
- `assets/textures/`
- `assets/audio/`
- `tests/`
- `docs/`
- `research/`

Evaluate whether migrating to Three.js would improve rendering, asset management, animation and long-term maintainability.

Three.js is preferred if the migration can preserve existing sailing physics and gameplay. Do not undertake a destructive rewrite simply to change rendering engines.

Keep simulation logic independent from rendering.

## 4. Phase One — Comprehensive audit and repairs

Before introducing major features, inspect and test the existing game.

Review:

- Camera orientation and coordinate systems
- Sail geometry and animation
- Wind and apparent wind calculations
- Sailing performance across different headings
- Rudder response
- Tacking and jibing behavior
- Reefing and independent sail contributions
- Boat movement across waves
- Walking on a moving vessel
- Deck collision boundaries
- Anchor behavior
- Auxiliary propulsion
- Autopilot
- Navigation chart accuracy
- Sailing Academy progression
- Touch input and multitouch
- Portrait and landscape layouts
- WebGL compatibility
- Mobile performance
- Audio initialization

Pay particular attention to whether the vessel's visual orientation matches its actual direction of travel.

Verify that wind direction indicators, compass headings, navigation bearings and sail orientation all use consistent coordinate conventions.

Fix any identified issues before expanding the game.

## 5. Phase Two — Meridian 26 vessel artwork overhaul

Replace the current primitive-looking vessel with a substantially more realistic cruising sailboat.

The fictional Meridian 26 is a modern Bermuda-rigged monohull cruising yacht.

Approximate specifications:

- Length: 26 feet
- Beam: 8.5 feet
- Draft: 4.5 feet
- Displacement: 2,500 kg
- Mainsail and jib
- Wheel steering
- Auxiliary diesel engine
- Compact cruising cabin

Treat these as initial design specifications and refine them if necessary for believable proportions.

Create or acquire appropriately licensed, optimized 3D assets for:

- Realistically curved fiberglass hull
- Keel and rudder
- Cockpit
- Teak or synthetic teak decking
- Stainless-steel steering wheel
- Helm pedestal
- Cockpit seating
- Cabin coachroof
- Companionway
- Hatches and windows
- Mast and boom
- Standing and running rigging
- Spreaders
- Winches
- Cleats
- Fairleads
- Lifelines
- Bow pulpit
- Anchor and chain
- Navigation lights
- Marine instruments

Use Blender when helpful and available. Prefer optimized GLB/glTF assets with physically based materials.

Avoid the appearance of simple cubes, cylinders and disconnected primitive shapes.

### Sail artwork and animation

Implement more natural sail shapes and deformation.

Sails should visually respond to:

- Apparent wind direction
- Apparent wind strength
- Sail trim
- Tacking
- Jibing
- Reefing
- Hoisting and lowering
- Luffing when improperly trimmed
- Gusts

Make sail configuration visually consistent with the underlying physics.

Sails must not clip extensively through the mast, deck, player camera or other sails.

## 6. Phase Three — First-person experience and animations

Improve the experience of physically standing aboard the vessel.

Implement:

- Natural first-person eye height
- Smooth walking acceleration and deceleration
- Proper deck collision
- Movement relative to the moving vessel
- Rail and hull boundaries
- Adjustable camera sensitivity
- Adjustable horizon stabilization
- Optional reduced-motion mode
- Context-sensitive equipment interaction
- Smooth transitions between walking and helm operation

### First-person hands

Create realistic first-person hands and forearms.

Develop animations for:

- Gripping the steering wheel
- Turning the wheel left and right
- Releasing the wheel
- Gripping and operating winches
- Pulling sail sheets
- Raising and lowering sails
- Operating the anchor
- Interacting with instruments

Use procedural animation, skeletal animation or inverse kinematics as appropriate.

Hands must connect convincingly to equipment. Avoid disconnected floating hands, excessive clipping or animations that obscure navigation.

Make first-person hands optional for accessibility and performance.

## 7. Phase Four — Walkable cabin interior

Create an accessible cabin below deck.

The player should be able to approach the companionway and descend into the cabin without leaving the vessel.

Include:

- Forward V-berth
- Seating and cushions
- Compact galley
- Navigation station
- Storage cabinets
- Interior lighting
- Windows and hatches
- Electrical panel
- Small dining area
- Equipment storage

The interior should feel like a compact cruising sailboat rather than a large room placed inside a hull.

Initially, prioritize functional interactions over complex survival systems.

The player should be able to:

- View nautical charts
- Check weather conditions
- Inspect onboard equipment
- Turn cabin lights on and off
- Rest or advance time
- Return to the cockpit

Autopilot should continue operating while the player explores the cabin, provided the vessel is underway and autopilot is engaged.

Maintain believable interior dimensions and collision boundaries.

## 8. Phase Five — Living Ocean 2.0

Significantly improve the ocean rendering and environmental simulation.

Study techniques used in realistic maritime simulators and modern 3D games. Use legitimate technical references and public documentation. Do not copy proprietary game assets or code.

Implement or improve:

- Multiple directional wave layers
- Wind-driven surface ripples
- Large ocean swells
- Wave-dependent buoyancy
- Physically plausible pitching and rolling
- Fresnel reflections
- Sunlight glitter
- Depth-based water coloration
- Turquoise shallows
- Deep-blue offshore water
- Whitecaps
- Breaking shoreline waves
- Hull foam
- Speed-dependent wakes
- Water spray where appropriate
- Atmospheric haze
- Cloud formations
- Horizon blending

The ocean should look expansive, natural and continuously moving.

Wave rendering and vessel buoyancy should use compatible wave calculations so the vessel does not visibly float above or sink through the water.

Provide Low, Medium, High and Automatic graphics settings.

Avoid sacrificing mobile playability for graphical effects.

## 9. Phase Six — The Azure Archipelago

Expand the game beyond the existing small island practice area.

Create an initial connected sailing region inspired by Caribbean and Mediterranean coastlines.

Introduce the following fictional destinations.

### Port Meridian

The primary starting location.

Include:

- Protected harbor
- Marina
- Floating docks
- Mooring posts
- Harbor entrance
- Breakwaters
- Navigation lights
- Lighthouse
- Sailing academy
- Boat dealership exterior
- Maintenance and fuel dock
- Waterfront buildings
- Other moored vessels

### Coral Bay

A tropical destination featuring:

- Sandy beaches
- Palm trees
- Clear turquoise water
- Protected anchorage
- Coral shallows
- Small coastal settlement

### Windward Isles

A destination intended for future competitive sailing.

Include:

- Open sailing channels
- Stronger winds
- Regatta buoys
- Navigational markers
- Suitable locations for future racing courses

### Northwatch Island

A mountainous island featuring:

- Rocky cliffs
- Elevated terrain
- Lighthouse
- Challenging coastal wind conditions
- Sheltered harbor or anchorage

### Sapphire Reef

A shallow-water navigation challenge.

Include:

- Visible reef formations
- Shallow water coloration
- Navigational hazards
- Marked channels
- Depth-based grounding behavior

### World scale

Long-term regional target: approximately 30 × 30 nautical miles.

For this release, prioritize a polished, genuinely traversable initial region of approximately 5 × 5 nautical miles or larger if performance permits.

These are design targets, not requirements to claim a larger world than actually exists.

Maintain consistent physical units for vessel dimensions, sailing speeds and distances.

Do not simply enlarge the existing islands without creating meaningful navigation and exploration opportunities.

Use procedural terrain, level-of-detail systems, world streaming and floating-origin techniques where beneficial.

## 10. Phase Seven — Docking, anchoring and harbor interactions

Introduce functioning harbor navigation.

Implement:

- Dock collision
- Breakwater collision
- Shoreline collision
- Shallow-water grounding
- Low-speed harbor maneuvering
- Forward and reverse auxiliary propulsion
- Adjustable engine throttle
- Mooring interaction
- Docking interaction
- Anchor deployment and retrieval
- Anchor holding behavior
- Appropriate depth restrictions
- Docking and departure assistance

Allow the player to leave Port Meridian, sail to another destination, enter its protected waters and dock or anchor.

Create a functional first voyage rather than disconnected scenery.

Do not immediately stop the vessel whenever the anchor is deployed. Model a simplified but believable transition involving vessel momentum and anchor holding forces.

## 11. Phase Eight — Functional navigation instruments

Build readable, functional instruments into the vessel itself.

Include:

- Magnetic compass
- Boat speed
- Speed over ground
- True wind speed
- Apparent wind speed
- Apparent wind angle
- Heading
- Course over ground
- Depth sounder
- Engine throttle and RPM
- Fuel indicator
- GPS chartplotter

Upgrade the navigation chart to include:

- Player location and heading
- Named islands and ports
- Harbor entrances
- Navigation buoys
- Shallow-water zones
- Depth information
- Compass orientation
- Distance scale in nautical miles
- Waypoint placement
- Route plotting
- Distance to destination
- Estimated arrival time
- Zoom and pan

Allow the player to select a destination on the chart and receive a navigation bearing.

Expand autopilot from heading hold to optional waypoint following.

Autopilot must respect sailing constraints. It should not magically propel the vessel directly into the wind.

If automatic tacking or obstacle avoidance is not implemented, clearly communicate that limitation.

## 12. Phase Nine — Dynamic weather and time

Introduce the foundation of a dynamic weather system.

Initial presets:

- Calm
- Light breeze
- Steady trade winds
- Overcast
- Strong winds
- Rain squall
- Fog

Implement gradually changing:

- Wind speed
- Wind direction
- Gusts
- Wave height
- Cloud coverage
- Visibility
- Lighting

Create a continuously progressing day-and-night cycle.

Allow players to configure:

- Starting time
- Starting weather
- Dynamic or fixed weather
- Time acceleration

Time acceleration must not destabilize the physics simulation or allow vessels to pass through obstacles.

Add functional lighthouse and vessel navigation lights during nighttime sailing.

## 13. Phase Ten — Expanded Sailing Academy

Retain the existing seven-stage tutorial and improve its instructional quality.

Create additional interactive lessons:

### Lesson 1 — Getting underway

Prepare the vessel, hoist sails and leave the anchorage.

### Lesson 2 — Points of sail

Teach:

- No-go zone
- Close-hauled
- Close reach
- Beam reach
- Broad reach
- Running

### Lesson 3 — Sail management

Teach:

- Mainsheet adjustment
- Jib sheet adjustment
- Luffing
- Reefing
- Sail efficiency

### Lesson 4 — Maneuvering

Teach tacking, jibing and heading control.

### Lesson 5 — Navigation

Use charts, bearings and waypoints to reach a destination.

### Lesson 6 — Harbor operations

Use the auxiliary engine, approach a dock and secure the vessel.

### Lesson 7 — Heavy weather

Recognize increasing wind, reef sails and maintain control.

Use concise contextual prompts and visual demonstrations.

The tutorials should teach through gameplay rather than large walls of text.

Do not present the simplified simulation as a substitute for real-world sailing instruction.

## 14. Phase Eleven — First exploration mission

Create the first meaningful open-world voyage.

### Mission: Across the Blue

Starting location: Port Meridian

Destination: Coral Bay

Objectives:

1. Inspect weather conditions.
2. Prepare the vessel.
3. Release mooring lines.
4. Depart Port Meridian.
5. Raise sails when appropriate.
6. Navigate toward Coral Bay.
7. Pass designated navigation markers.
8. Enter the protected bay.
9. Anchor safely.
10. Complete the voyage.

Include optional objectives for efficient sail trimming, safe maneuvering and engine conservation.

Provide a voyage summary containing:

- Distance traveled
- Elapsed time
- Average speed
- Maximum speed
- Engine usage
- Sail efficiency
- Navigational accuracy
- Completed objectives

Do not require a full career economy for this mission.

It should establish the foundation for future contracts, exploration activities, yacht deliveries and racing.

## 15. Phase Twelve — Mobile interface improvements

The game must remain playable on iPhone in portrait and landscape orientation.

Prioritize landscape for panoramic sailing while maintaining portrait functionality.

Preserve:

- Left-thumb steering and walking
- Drag-to-look camera
- Independent sail controls
- Contextual interactions
- Camera switching

Improve:

- Safe-area handling
- Readability
- Button sizes
- Control spacing
- Multitouch reliability
- Orientation changes
- Prevention of accidental browser zoom
- Fullscreen presentation where supported

Add easily accessible controls for:

- Camera view
- Rigging
- Chart
- Autopilot
- Engine
- Contextual interaction

Consider a collapsible sailing control panel so the player can enjoy an unobstructed ocean view.

Never require a keyboard for mobile gameplay.

## 16. Performance requirements

Target iPhone Safari and desktop browsers.

Performance targets:

- Stable 30 FPS on supported mobile hardware
- 60 FPS where hardware permits
- Mobile p95 frame time at or below 33.3 ms as a target
- Responsive touch input
- No recurring major frame stalls
- Controlled memory usage

Use:

- Adaptive rendering resolution
- Instanced environment objects
- Frustum culling
- Level-of-detail models
- Texture optimization
- Asset compression
- Object pooling
- Efficient shader programs
- Limited dynamic lighting
- Independent physics and rendering updates

Measure actual performance rather than estimating it.

If physical iPhone testing is unavailable, document that clearly and conduct the strongest available browser-based testing.

## 17. Multi-agent development structure

If your environment supports agent teams or subagents, divide the work into coordinated responsibilities.

Suggested agents:

**Lead Architect:** Repository organization, architecture, integration and release management.

**Marine Simulation Engineer:** Wind, sails, buoyancy, rudder, engine, anchoring and grounding.

**Vessel Artist:** Hull, cockpit, rigging, sails, cabin and materials.

**Environment Artist:** Ocean rendering, islands, harbors, weather, vegetation and lighting.

**First-Person Gameplay Engineer:** Player movement, hands, equipment interactions and cameras.

**Navigation and UX Engineer:** Instruments, charts, autopilot, tutorials and mobile interface.

**QA Engineer:** Automated tests, browser testing, regression testing and performance verification.

**Research Documentation Agent:** Preserve prompts, decisions, development cycles, test evidence, reflection records and release documentation.

Avoid having multiple agents modify the same files simultaneously without coordination.

If subagents are unavailable, perform these responsibilities sequentially.

## 18. Testing requirements

Maintain and expand automated testing.

Test:

- Wind-dependent acceleration
- No-go zone behavior
- Apparent wind
- Independent sail configurations
- Reefing
- Tacking and jibing
- Boat stability
- Wave-driven vessel movement
- Engine throttle and reverse
- Anchor deployment
- Grounding
- Dock collisions
- Walking on a moving vessel
- Cabin entry and exit
- Camera switching while underway
- Navigation bearings
- Waypoint placement
- Autopilot behavior
- Tutorial progression
- Mission completion
- Save/load behavior
- Mobile multitouch
- Orientation changes
- WebGL context failure and recovery behavior

Use Playwright or an equivalent browser-testing framework where available.

Capture actual gameplay screenshots in portrait and landscape.

Required visual verification:

- First-person helm
- Wide helm
- Bow camera
- Masthead camera
- Chase camera
- Cockpit winch interaction
- Cabin interior
- Port Meridian
- Open ocean
- Coral Bay
- Navigation chart
- Night sailing
- Heavy weather
- Docking

Do not substitute AI-generated concept art for actual gameplay screenshots.

## 19. Dissertation research and documentation

This project is part of an ongoing game-development research process.

Preserve every user development prompt and every assistant-generated implementation or handoff prompt verbatim.

Maintain a private research archive containing:

- Original user prompts
- Original AI-generated prompts
- Relevant AI responses
- Design rationale
- Development decisions
- Technical failures
- Iterations and corrections
- Testing methodology
- Actual test results
- Screenshots
- Performance measurements
- Development cycle records
- Reflection journals
- Release notes
- Git commit references
- Timestamps
- AI model information when known

Suggested research structure:

- `research/prompts/user/`
- `research/prompts/ai-handoffs/`
- `research/ai-responses/`
- `research/development-cycles/`
- `research/reflections/`
- `research/testing-evidence/`
- `research/screenshots/`
- `research/artifact-register.md`
- `research/research-index.md`

Clearly distinguish verbatim records from retrospective analysis.

Do not invent personal reflections, research findings or user experiences. Identify AI-generated reflections as such and leave space for researcher-authored observations.

Archive this complete handoff verbatim before implementing changes.

Keep all research documentation private and exclude it from public runtime deployments.

## 20. Release and deliverables

Develop incrementally and preserve intermediate working milestones.

Suggested milestones:

- v0.4-alpha.1 — Architecture and Stability
- v0.4-alpha.2 — Meridian Reforged
- v0.4-alpha.3 — Life Aboard
- v0.4-alpha.4 — The Azure Archipelago
- v0.4-alpha.5 — Navigation and Harbor Operations
- v0.4-alpha.6 — Across the Blue
- v0.4 — Beyond the Harbor

Only assign a milestone version when the corresponding functionality is actually implemented and tested.

At the end of the development session, provide:

1. A playable preview link or locally runnable build.
2. Updated source code.
3. GitHub branch and commit references, if GitHub access is available.
4. A detailed changelog.
5. Actual gameplay screenshots.
6. Automated test results.
7. Mobile browser testing results.
8. Performance measurements where available.
9. Known issues and limitations.
10. Updated research documentation.
11. Recommendations for the next development iteration.

Preserve all previous working previews.

If public deployment requires authorization, obtain it before publishing. Otherwise, use an authorized private preview or local build.

## Final development directive

The long-term vision is to create a maritime equivalent of Microsoft Flight Simulator, combined with the first-person immersion of Sea of Thieves and the exploration, progression and ownership systems of an open-world RPG.

True Bearing should become a game where players can spend an afternoon peacefully sailing through tropical waters, navigate challenging weather, learn realistic sailing techniques, explore distant ports, purchase and customize vessels and eventually compete in major ocean races.

Prioritize realism, immersion, accessibility and enjoyable sailing.

Do not rush through the visual work. Make the vessel and ocean convincing environments that players genuinely want to spend time in.

Begin by recovering and auditing the current v0.3-alpha.1 build, preserving the existing release, establishing the development branch and implementing the upgrades in the order that produces the strongest reliable playable result.

Do not stop at producing a plan. Implement, test, evaluate, refine and deliver the game.