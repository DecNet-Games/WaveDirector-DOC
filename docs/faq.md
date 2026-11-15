---
layout: default
title: FAQ
nav_order: 8
---

# Frequently Asked Questions

**Is this a behaviour-tree framework?**
No. It is an encounter director: difficulty curves, wave budgets, spawning and pacing telemetry. Enemy decision-making inside a wave is your game's (or your behaviour framework's) job — see [Limitations]({{ site.baseurl }}/docs/limitations/).

**Will the same settings always produce the same wave?**
Yes. Composition is deterministic given (curve, wave index, seed), and each composition carries a hash you can log and compare.

**Can I use my own spawner and enemy prefabs?**
Yes. Integration is interface-based (`IDirectorSpawner`); pooling for your prefabs is built in.

**What if my curve data is wrong?**
Validation reports the problem naming the curve — a missing control point or an inverted plateau range never becomes a silent flat line.

**Does it work for a genre that is not tower defense or survivors-like?**
The director's model (curve → budget → composition) is genre-agnostic, and a third preset ships in the box; the two named genres are the ones with dedicated spawn modes and demo scenes.

**Where do I get support?**
support@decnetgames.com.
