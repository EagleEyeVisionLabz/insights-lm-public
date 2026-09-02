# M5 MacBook Debloat & Core Remap

Goal: free space and speed so the current MVP (Plane + Colanode + Płane + Open Knowledge + Open Notebook + InsightsLM) runs fast on the M5.

## Keep (current stack, last 1–2 weeks)

- InsightsLM (this fork)
- plane-integration
- M3TA-OPEN-KNOWLEDGE (canonical Open Knowledge vault)
- M3ta-Hueman-Agentic-OS (core agentic OS)
- m3ta-empire (model evals + adapters)
- Open Notebook / Open Knowledge installs (local)

## Deprecate / archive (older, superseded)

- M3ta-OS-OpenKnowledge → merge unique content into M3TA-OPEN-KNOWLEDGE, then archive
- Qu3bii-Sovereign-Agentic-OS → superseded by M3ta-Hueman-Agentic-OS
- Qu3bii-Da-Pope-Bot, qu3bii-command-center → old voice experiments
- OpenMontage-m3ta-0s → video pipeline, not core to current MVP
- m3ta-icloud-workspace, m3TAz-wURLd-ikb-vault → old vaults
- npo-hero, edge-hydration, builder-brokers, Pheonyx.a3y3 → side projects outside current focus
- apps, c0achm3ta, agentjob-srt-smoke, priceless-torvalds-283048 → legacy

## Local disk sweep (run on the Mac)

```bash
# Docker reclaim (biggest win for InsightsLM + Plane)
docker system df
docker system prune -af --volumes

# Common AI / agent hogs
rm -rf ~/Library/Application\ Support/Cursor/User/globalStorage/state.vscdb.backup
du -sh ~/Library/Application\ Support/Docker\ Desktop 2>/dev/null
du -sh ~/.ollama 2>/dev/null

# Old node_modules / build artifacts in deprecated repos
find ~/Projects -maxdepth 3 -type d -name node_modules -prune -exec rm -rf {} +
```

## Order of operations

1. Archive deprecated GitHub repos (this week).
2. Run Docker prune + cache sweep.
3. Install InsightsLM + Plane via Docker only after space is freed.
4. Point audit pipeline at Plane; stop writing to Linear.
