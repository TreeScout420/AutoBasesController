# AutoBasesController

A Discord bot that provides advanced spawn control for the Auto Bases Ascended plugin in ARK: Survival Ascended.

## Features

- Controls AutoBases spawning through RCON
- Tracks active and completed base events from Discord webhook messages
- Supports per-map and cluster-wide spawn scheduling
- Supports map caps, cooldowns, and weighted spawn groups
- Includes a live dashboard and admin commands
- Uses lightweight JSON files instead of a database
- Supports optional TribeLogsAscended raid tracking
- Tracks attacking tribes, tribe IDs, destroyers, and destroyed structures
- Supports one combined TribeLogsAscended feed across multiple maps/servers
- Can post completed raid reports to a dedicated Discord channel
- Uses a configurable completion grace period to catch late destruction log messages
- Maintains a configurable rolling raid history in `raid_history.log`

## Raid Tracking Requirements

Raid tracking is optional and requires the TribeLogsAscended plugin.

AutoBases templates used with raid tracking must have:

- `TribeIdOverride = -1`
- or `TribeIdOverride > 50000`

The bot must also be able to read the configured TribeLogsAscended Discord channel.

## Configuration

AutoBasesController uses a `config.json` file for:

- Discord channels
- RCON servers
- scheduler settings
- maps
- cooldowns
- spawn groups
- cluster-wide limits
- in-game announcements
- optional TribeLogsAscended raid tracking
- optional completed raid report channel
- raid completion grace period

A full template, annotated config example, and detailed README are included in the release download.

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
