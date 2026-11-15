# PUSH NOTE — WaveDirector-DOC (internal, not part of the site)

- Built 2026-11-13 (VM phase) under `~/workspace/decnet-builds/wave-director/docsite/`, following `~/workspace/marketing-packages/DOC-SITE-STANDARD.md` (Jekyll + Just the Docs, remote_theme, github-pages Gemfile).
- Intended repo: `DecNet-Games/WaveDirector-DOC`; intended live URL: `https://decnet-games.github.io/WaveDirector-DOC/` (matches `_config.yml` baseurl).
- NOT deployed, NOT pushed. Deployment is a later step: repo created via GitHub web UI, content pushed via the proven gh-connect SSH-over-443 route, live URL curl-verified 200 + media visible (standard §6–§7).
- Media status: cover + 2 hero images embedded from the product's composed marketing art. Demo video and feature GIFs do NOT exist yet — they come from the capture phase (real demo-scene and pacing-graph captures); per the standard, the site is not "complete" until that media lands in a follow-up commit.
- Claims: feature claims trace to SPEC.md §6 fence; API page grounded in the shipped package source (`run2/pkg/Runtime`, namespace `Decnet.WaveDirector`). Open item before this site goes live: dual-version verification is INCOMPLETE (BUILD-LOG.md 2026-11-13 — graphics-enabled rerun staged, laptop pending), so the site deliberately makes no "verified on both versions" claim — add it only when the drain verdict lands.
- Banned-term grep over the site: clean.
