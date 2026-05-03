# AutoBasesController

A Discord bot that provides advanced spawn control for the Auto Bases Ascended plugin in ARK: Survival Ascended.

## Features

- Controls AutoBases spawning through RCON
- Tracks active and completed base events from Discord webhook messages
- Supports per-map and cluster-wide spawn scheduling
- Supports map caps, cooldowns, and weighted spawn groups
- Includes a live dashboard and admin commands
- Uses lightweight JSON files instead of a database

## Configuration

AutoBasesController uses a `config.json` file for Discord channels, RCON servers, scheduler settings, maps, cooldowns, and spawn groups.

A full template and annotated example are included in the release download.

Minimal map example:

```json
{
  "maps": {
    "rag": {
      "plugin_map_name": "Ragnarok_WP",
      "enabled": true,
      "max_active": 1,
      "cooldown_minutes": 120,
      "spawn_interval_minutes": 121,
      "spawn_groups": [
        { "name": "Tier2", "weight": 1 }
      ]
    }
  }
}
