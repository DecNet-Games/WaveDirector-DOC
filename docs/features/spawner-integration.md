---
layout: default
title: Spawner Integration
parent: Features
nav_order: 3
---

# Spawner Integration

One director, two spawn modes — your spawner wires to the director's events, not the other way round.

## Tower-defense mode

Waves spawn at path entry points on the director's schedule: wave start, inter-wave gap, spawn cadence within a wave. Spawn points receive exactly the composed wave, and the wave-end event fires when the wave is cleared.

## Survivors-like mode

Continuous pressure spawning around the player. Spawn rate and mix track the curve value over time — rate rises with difficulty, mix shifts per the composition rules — and the director's throttle caps the live spawned count at its documented limit.

## The integration contract

- **Interface-based.** Your spawner implements `IDirectorSpawner` and receives `SpawnRequest`s. A stub spawner drives the full director with no changes to director code.
- **Events in a documented order** — wave started → spawn issued → wave cleared / pressure tick. Pause and resume mid-wave without losing the composed wave or double-spawning.
- **Failure isolation.** A spawner that throws is isolated: the director logs the failure and continues the wave; your spawner's bug never crashes the run.
- **Pooling built in.** Spawned enemies come from pools (`GameObjectPool` / pooled spawner bridge), so high-count waves do not pay per-spawn allocation costs.
- **Mode switching is safe.** Reconfigure a project from tower-defense to survivors-like mode and it composes valid waves under the same curve and budget rules.

![Horde scale, under direction]({{ site.baseurl }}/assets/images/hero-02.png)
