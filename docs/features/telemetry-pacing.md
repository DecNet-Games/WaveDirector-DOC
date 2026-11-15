---
layout: default
title: Telemetry & the Pacing Graph
parent: Features
nav_order: 4
---

# Telemetry & the Pacing Graph

The proof of depth: the director shows you your own pacing instead of letting you guess it.

## What gets recorded

During a run, the director records per-wave telemetry: wave index, curve difficulty value, budget spent, enemies spawned and killed, wave duration, player damage taken, and player health at wave end. A scripted playtest produces a complete record — every wave, every documented field — saved as a data artifact (CSV/JSON).

## The pacing graph

The graph is generated from the recorded telemetry: curve values and outcome values per wave, plotted together. A record-vs-graph comparison test asserts the graph matches the record exactly — the graph is drawn from data, never by hand.

## Reproducible

The same scripted run with the same seed produces the same telemetry values within a stated tolerance, recorded in the verification record.

## Yours to use

Telemetry hooks are part of the public surface: a subscriber to the documented telemetry events receives the same per-wave values as the recorded artifact, so you can record your own playtests your own way — and the editor's telemetry viewer renders the graph inside Unity.
