---
layout: default
title: Installation
nav_order: 3
---

# Installation

The Procedural Wave & Encounter Director is a **commercial Unity Asset Store product**. Purchase and installation happen through the Asset Store — it is not available as a free download.

{: .important }
> Buyers install from the Unity Asset Store only.

---

## Requirements

- **Unity 2022.3 LTS or Unity 6 (6000.x).**
- Runtime paths never require the editor: curve evaluation and composition run in a built player.
- Data loads from `Resources` (curves, rosters, rule sets) — no external dependency.

## Steps

1. Purchase the package on the Unity Asset Store.
2. In Unity, open the Package Manager and import it from **My Assets**.
3. Open a demo scene and press Play — a preset is already loaded, and the director runs the waves.
4. Load a preset in your own scene and run your first directed wave (see the [Quick Start]({{ site.baseurl }}/docs/quick-start/)).

## What is in the package

| Part | Contents |
|---|---|
| Curve engine | Difficulty curves as data (segments, plateaus, spikes), deterministic evaluation |
| Budget system | Cost tables, composition rules, deterministic wave composition |
| Spawner integration | Tower-defense + survivors-like modes, event stream, built-in pooling |
| Telemetry | Per-wave records + pacing graph generation |
| Presets & scenes | 3 genre presets (data) + 3 playable demo scenes |
| Editor tooling | Curve editor, budget inspector, wave timeline, telemetry viewer |
| Tests | The full test suite, with a README on how to run it |
