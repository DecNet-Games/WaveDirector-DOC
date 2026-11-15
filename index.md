---
layout: default
title: Home
nav_order: 1
---

# Stop hand-tuning wave tables. Direct your encounters.

![Procedural Wave & Encounter Director]({{ site.baseurl }}/assets/images/cover.png)

<video controls preload="metadata" style="max-width:100%" poster="{{ site.baseurl }}/assets/images/cover.png">
  <source src="{{ site.baseurl }}/assets/video/demo.mp4" type="video/mp4">
</video>

Every tower-defense and survivors-like game lives or dies on encounter pacing — and nearly every team tunes that pacing by hand, wave table by wave table, in a spreadsheet, until it feels right. The **Procedural Wave & Encounter Director** replaces the spreadsheet: you design the difficulty curve, the director turns it into waves built to a budget, and playtest telemetry shows you your own pacing graph.

---

## What it does

- **Difficulty-curve engine** — difficulty is a curve you design over the run: rising segments, plateaus, spikes for boss and elite waves. Curves are data, evaluated deterministically — the same curve at the same wave always returns the same difficulty.
- **Budget-based spawning** — each wave gets a spawn budget from the curve; enemy types cost budget points from a data-driven cost table; the director composes a wave that fits the budget and obeys composition rules (elite caps, minimum variety, boss-wave composition). Same curve, wave and seed → the same wave.
- **Two spawn modes, one director** — tower-defense waves at path entry points on the director's schedule, and survivors-like pressure spawning around the player, throttled by the same curve and budget. Integration is interface-based, with built-in enemy pooling.
- **Playtest telemetry + pacing graph** — per-wave records (difficulty, budget spent, spawned/killed, duration, damage taken, health at wave end) drawn as a pacing graph: designed difficulty against actual outcome.
- **Three genre presets + three demo scenes** — complete, measurably different configurations, each a data file you can duplicate and retune, each with its own playable demo scene.
- **Editor tooling** — a curve editor, a budget inspector whose preview matches runtime composition, a wave timeline, and the telemetry viewer. Every action undoable; nothing silently rewrites your data or scene.

![Pressure spawning, directed]({{ site.baseurl }}/assets/images/hero-01.png)

---

## The honesty policy

The pacing-graph claim in these docs rests on telemetry recorded from real runs: the graph is generated from the record, never drawn to look good. What the director does not do (it is not a behaviour-tree framework, and it does not make your enemies smart) is stated in [Limitations]({{ site.baseurl }}/docs/limitations/).

---

## Quick links

- [Getting Started]({{ site.baseurl }}/docs/getting-started/) — core concepts in five minutes
- [Installation]({{ site.baseurl }}/docs/installation/) — Asset Store purchase and setup
- [Quick Start]({{ site.baseurl }}/docs/quick-start/) — load a preset, run your first directed wave, read your first pacing graph
- [Features]({{ site.baseurl }}/docs/features/) — deep dives on every system
- [API Reference]({{ site.baseurl }}/docs/api/) — the real public surface
- [Presets & Demo Scenes]({{ site.baseurl }}/docs/samples/)
- [FAQ]({{ site.baseurl }}/docs/faq/)
- [Limitations]({{ site.baseurl }}/docs/limitations/)

---

*Procedural Wave & Encounter Director is a commercial Unity product by DecNet Games. Built for Unity 2022.3 LTS and Unity 6. Support: support@decnetgames.com.*
