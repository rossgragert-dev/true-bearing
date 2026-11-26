# Development baseline — 2026-11-26

## Live release history
- v0.1 First Wind: local HTML and ZIP; archived source in `archive/v0.1/`.
- v0.2 Living Ocean: local HTML and ZIP; archived source in `archive/v0.2/`.
- v0.2.1 Living Ocean compatibility preview: https://keen-beamlet-csv5u5e.shipstatic.com
- v0.2.2 Clear Horizon: https://driven-nano-sc5h3pz.shipstatic.com
- v0.3-alpha.1 Master the Rig: https://shaded-comet-h636eyt.shipstatic.com

The latest public preview is the intended baseline. Recover its actual index.html with curl or a browser on a network-enabled machine, record a checksum, verify version and five cameras, and commit it as a preserved baseline before changing gameplay. This session could not resolve the preview hostname from its local container. The archived v0.3 physics-check file is a separate local test artifact, NOT the full deployed runtime. Do not use it as the current game without reconciliation. Earlier source and README files are text copies recovered from conversation attachments, not byte-verified ZIP extractions.

## Current reported functionality
First-person helm and walking; wide helm, bow, masthead, chase camera; wind, apparent wind, momentum, heel, pitch, leeway; combined and independent sail trim, raising and lowering, reefing, winches, tacking; heading hold, anchor, auxiliary propulsion; charts and practice buoy navigation; day, sunset, night; ocean audio; seven-stage Sailing Academy. Original custom WebGL renderer and JavaScript, no external runtime dependencies.

## Evidence and limitations
- v0.1: 9/9 physics checks reported; JavaScript syntax checked; browser WebGL unavailable.
- v0.2: 14/14 physics checks reported; two shader programs compiled and linked; three native software-rendered captures; mobile controls and performance unverified.
- v0.2.1: public compatibility build with reduced pixel ratio, antialiasing disabled, WebGL fallback and diagnostic messaging.
- v0.2.2: five cameras and next-mark bearing added. User said prior build was looking good; new camera behavior not independently device-tested.
- v0.3-alpha.1: 21/21 reported local physics/rigging checks (14 prior, 7 new); deployed preview; no verified end-to-end mobile tutorial or browser performance.
These are historical reports, not newly reproduced results. Rerun tests and compare exact deployed code before relying on them.

## Next release
Beyond the Harbor: stable modular architecture, higher-quality yacht and ocean, meaningful connected destinations, navigation, docking, and first voyage. Prioritize an incremental playable vertical slice. See HANDOFF.md.

## Archive material
Original v0.1 and v0.2 ZIPs were created in ChatGPT and include additional tests, research cycle documents and, for v0.2, screenshots and rendering scripts. They remain available in the originating chat attachments; current repository archive includes the recovered text files, not the complete binary ZIPs. No public deployment was modified during this documentation import.
