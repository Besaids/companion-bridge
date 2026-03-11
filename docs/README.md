# Documentation

This folder explains how the architecture works and how to build your own package without touching the bundled example case.

## Guides

- [architecture.md](architecture.md) - How the files cooperate and why the setup transfers across models
- [build-your-own.md](build-your-own.md) - Three build modes: blank self-evolving, seeded bootstart, and reconstruction from logs
- [agent-workflow.md](agent-workflow.md) - How to use an agent to interview the user, inspect exports, draft a package, and iterate
- [extract-from-logs.md](extract-from-logs.md) - How to turn raw chat history into a usable companion package
- [maintenance.md](maintenance.md) - Session loop, monthly cadence, calibration, and drift correction

## Notes

- `example-case/` is the standalone fictional package.
- `showcase/` is the standalone transcript set generated from that package.
- Those folders are reference artifacts, not step-by-step documentation.
- If you are using an editor agent, keep your raw exports outside the example package and treat this repo as the scaffold the agent writes into.

If you only want to load the example, the top-level [README.md](../README.md) is enough.
If you want to build your own system, start with [build-your-own.md](build-your-own.md).
