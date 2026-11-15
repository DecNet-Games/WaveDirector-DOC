---
layout: default
title: API Reference
nav_order: 6
---

# API Reference

The public surface lives in the `Decnet.WaveDirector` namespace (core logic in `Decnet.WaveDirector.Core`, diagnostics in `Decnet.WaveDirector.Diagnostics`). The runtime assembly is `Decnet.WaveDirector.Runtime`. This page lists the stable entry points; the offline reference inside the package documents every signature and matches this site's version.

## Core types

| Type | Role |
|---|---|
| `EncounterDirector` | The director itself: evaluates the curve, composes waves, drives spawners, records telemetry |
| `EncounterDirectorBehaviour` | MonoBehaviour host implementing `IDirectorSpawner` for scene use |
| `DifficultyCurve` / `CurveSegment` | Curve data: segments with kinds (rise, plateau, spike), wave ranges and values |
| `DirectorConfig` | Run configuration: spawn mode, spread pattern, limits |
| `EnemyRoster` / `EnemyDefinition` | Enemy types and their budget costs |
| `CompositionRules` / `CompositionResult` | The rule set (caps, variety, boss composition) and a composed wave's result, including its composition hash |
| `DeterministicRandom` | The seeded random source behind deterministic composition |
| `ValidationReport` / `ValidationIssue` | Data-validation output: malformed curves, costs and rosters are reported here, naming the entry |

## Integrating your spawner

Implement the interface and the director feeds you:

```csharp
public interface IDirectorSpawner
{
    void Spawn(SpawnRequest request);
}
```

`SpawnRequest` carries the enemy `TypeId`, `Wave`, `Tick`, `SequenceIndex`, `SpawnPointIndex`, `SpreadPattern` and `TimeOffsetSeconds`. `NullDirectorSpawner` is included for headless runs and tests; `PooledSpawnerBridge` routes requests into the pooling system (`GameObjectPool`, `SpawnPoolRegistry`, `PrefabPoolSet`).

## Events

`DirectorEvent`s fire in a documented order — wave started → spawn issued → wave cleared / pressure tick (`DirectorEventKind`) — and each spawn event carries the wave's `CompositionHash`, so your logs can prove which composition a spawn came from. Director lifecycle is observable through `DirectorState`.

## Data loading

Curves, rosters and rule sets load from `Resources`:

- `DecnetWaveDirector/Curves` — defaults: curve `td_standard`
- `DecnetWaveDirector/Rosters` — defaults: roster `core_roster`
- `DecnetWaveDirector/Rules` — defaults: rules `core_rules`

`WaveDirectorData.LoadAllFromResources()` loads all three sets; `GetCurve(id)`, `GetRoster(id)` and `GetRules(id)` fetch by ID, with `DefaultCurve` / `DefaultRoster` / `DefaultRules` shortcuts. Logging plugs in through `IWaveDirectorLogger` (a Unity logger implementation is included).
