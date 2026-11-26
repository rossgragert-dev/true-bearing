# true-bearing

# True Bearing — development hub

First-person open-world sailing simulator, combining simulation, exploration, career progression and racing.

**Current preview:** [v0.3-alpha.1 — Master the Rig](https://shaded-comet-h636eyt.shipstatic.com)

## Start here
- [Claude implementation entry point](docs/HANDOFF.md) — updated to use this repository.
- [Full original Beyond the Harbor handoff](research/prompts/ai-handoffs/2026-11-26-beyond-the-harbor.md) — historical prompt, preserve unchanged.
- [Baseline and release history](docs/BASELINE.md)
- [Research index](research/INDEX.md)
- [Artifact register](research/artifact-register.md)
- [Archived source and evidence](archive/)

Recover and verify the exact v0.3-alpha.1 runtime before implementation. The local v0.3 physics-check HTML is not the deployed runtime. Earlier source is preserved for reference. Keep this repository private, do not publish research files, do not delete local files or overwrite working previews. Work on an isolated branch and record actual test results.

To run the recovered v0.2 simulation checks: `node archive/v0.2/physics-test.cjs` (Node required; these are historical tests, not an end-to-end browser verification).
