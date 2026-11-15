---
layout: default
title: Presets & Editor Tooling
parent: Features
nav_order: 5
---

# Presets & Editor Tooling

## Three genre presets

Each preset is a complete, tuned configuration — curve + budget costs + composition rules + spawn mode + demo tuning — that loads and plays immediately. Tower defense and survivors-like are two of the three; the presets differ measurably: their curve shapes and composition rules are not copies of each other, and a comparison test asserts their wave compositions differ on the same wave indices.

Presets are data files in the package. Duplicate one, change its curve, run it — no code touched.

## The editor workflow

- **Curve editor** — see and edit the difficulty curve as a graph; editing a control point changes the evaluated difficulty by the documented amount.
- **Budget inspector** — wave budget, enemy costs, and a composition preview for a chosen wave that matches the runtime composition for the same inputs.
- **Wave timeline** — every wave in the run with its difficulty, budget and composition; a known wave set shows exactly those waves, no invented rows.
- **Telemetry viewer** — the pacing graph inside the editor, from a recorded playtest.

Built on one rule: **the tooling never destroys your scene or data.** Every editor action is undoable through Unity's undo system, and no action silently rewrites a preset, a curve or a scene. A fresh empty scene plus the default preset produces a valid session.
