---
layout: default
title: Quick Start
nav_order: 4
---

# Quick Start — a preset, a wave, a pacing graph

1. **Add the director to a scene.** A fresh empty scene plus the default preset produces a valid director session — no missing references, no setup ritual. Out of the box the defaults are the `td_standard` curve, the `core_roster` roster and the `core_rules` rule set.
2. **Press Play.** In tower-defense mode the director starts waves on its schedule; spawn points receive exactly the composed waves; the wave-cleared event fires when a wave is done.
3. **Open the budget inspector** and pick wave 10. The composition preview it shows is the same composition the runtime will produce for wave 10 — preview and runtime agree.
4. **Edit the curve.** Drag a control point in the curve editor; the evaluated difficulty for the affected waves changes by the documented amount. Undo works on every edit.
5. **Run a playtest and open the telemetry viewer.** Your run's pacing graph is there: designed difficulty against actual outcome, wave by wave. Find the wave where the two lines disagree — that is your next tuning decision.

From here: [Difficulty Curves]({{ site.baseurl }}/docs/features/difficulty-curves/) documents the curve model, [Budget-Based Spawning]({{ site.baseurl }}/docs/features/budget-spawning/) the composition rules, and the [API Reference]({{ site.baseurl }}/docs/api/) the code surface.
