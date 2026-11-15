---
layout: default
title: Budget-Based Spawning
parent: Features
nav_order: 2
---

# Budget-Based Spawning

The arithmetic that turns difficulty into enemies — and the system's honesty check.

## How a wave is composed

1. The wave's difficulty value comes from the curve.
2. That value becomes a **spawn budget**.
3. Each enemy type **costs budget points** from a data-driven cost table.
4. The director composes a wave whose total cost fits the budget, respecting **composition rules**: elite caps per wave, minimum variety, and boss waves that spend the budget on the boss plus escorts.

## Guarantees (asserted across the verification wave set)

- **Budget fit.** Every composed wave's total cost is at or under its budget, and at or above the documented minimum utilisation — no wave ships nearly empty unless its rule set says so.
- **Zero rule violations.** Elite caps, boss composition and variety rules hold in every composed wave in the test set.
- **Deterministic.** Given (curve, wave index, seed), replaying reproduces the same wave-composition hash.
- **Costs are data.** Add a test enemy type with a cost as a data file only and it becomes eligible for composition. Negative cost, a missing type or a cost with no enemy is reported naming the entry.
- **Degenerate inputs degrade gracefully.** A zero budget or an empty roster produces an empty wave with a logged warning — never an exception, never an infinite composition loop.
