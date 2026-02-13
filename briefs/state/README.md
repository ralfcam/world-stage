# briefs/state/README.md

This directory contains GitHub-native “state” used for narrative continuity without running a Temporal Knowledge Graph.

Files:
- `state_pack.md`: single-file continuity bundle for Tasks (preferred read).
- `continuity_last7d.md`: rolling human-readable digest (overwrite daily).
- `active_narratives.yml`: machine-friendly registry (overwrite daily).

These files are intentionally small so Tasks can retrieve them quickly with MCP.
