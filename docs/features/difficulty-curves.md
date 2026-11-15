---
layout: default
title: Difficulty Curves
parent: Features
nav_order: 1
---

# Difficulty Curves

The core model. You define how difficulty rises over a run — a curve over waves and time, built from segments:

- **Rising segments** that climb at a stated slope.
- **Plateaus** that hold their value across a stated wave range — breathing room, placed deliberately.
- **Spikes** that evaluate at a stated multiplier for a wave — boss and elite moments.

Each shape behaves per its documented definition, asserted by a fixed test set per shape.

## Deterministic evaluation

The same curve plus the same wave index returns the same difficulty value, on both supported Unity versions, asserted across a fixed set of wave indices. There is no hidden randomness in evaluation.

## Curves are data

Add a test curve as a data file only — no code change — and the engine evaluates it. Malformed curve data (a missing control point, a negative wave index, a spike with no magnitude, a plateau with an inverted range) is reported with a clear error naming the curve: never a silent flat line, never a crash.
