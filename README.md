<div align="center">
  <img src="docs/images/waybinder-logo.png" alt="Waybinder logo" width="128" height="128">

# Waybinder

**Homes, warps, TPA, `/back`, and configurable random teleportation in one lightweight Fabric utility mod.**

Minecraft **26.3** · Fabric · Java **25+**
</div>

## About

Waybinder brings the most useful multiplayer teleport commands into one configurable mod without turning them into a giant server-management system.

It started as a fork of **Simple Warp TPA Home Back** by ZiYun. **FastRTP** by Wesley1808 was later integrated directly, and the project has since been expanded, redesigned, and maintained as Waybinder by **Kukiz**.

The current stable release is **1.2.0** for Minecraft **26.3**.

## Features

- Personal homes with a selectable main home.
- Public server warps.
- `/tpa` and `/tpahere` requests with timeout, cooldown, and dimension policies.
- `/back` for normal teleport/death return points.
- `/rtp` with configurable radius, cooldown, dimensions, biome restrictions, ocean avoidance, and safe-location checks.
- Separate `/rtpback` tracking the destination of the most recent successful random teleport.
- Server-authoritative settings with permission-aware editing.
- In-game configuration through Mod Menu + YACL.
- Custom biome and biome-group blacklist editor.
- Built-in About and Changelog screens.

## Commands

### Homes

| Command | Description |
| --- | --- |
| `/sethome <name>` | Create a home at your current position. |
| `/home` | Teleport to your selected main home. |
| `/home <name>` | Teleport to a named home. |
| `/homes` | List your homes. |
| `/delhome <name>` | Delete a home. |
| `/setmainhome <name>` | Choose which home plain `/home` uses. |
| `/clearmainhome` | Clear the selected main home. |

### Teleport requests

| Command | Description |
| --- | --- |
| `/tpa <player>` | Ask to teleport to another player. |
| `/tpahere <player>` | Ask another player to teleport to you. |
| `/tpaccept` | Accept the current teleport request. |
| `/tpdeny` | Deny the current teleport request. |

### Public warps

| Command | Description |
| --- | --- |
| `/warp <name>` | Teleport to a public warp. |
| `/warps` | List public warps. |
| `/setwarp <name>` | Create or update a public warp when permitted. |
| `/delwarp <name>` | Delete a public warp when permitted. |

### Return and random teleport

| Command | Description |
| --- | --- |
| `/back` | Return to the latest normal Waybinder return point, such as a previous teleport position or death location. |
| `/rtp` | Randomly teleport to a safe allowed location. |
| `/rtpback` | Return to the destination of your most recent successful `/rtp`. |

### Administration

| Command | Description |
| --- | --- |
| `/waybinderconfig` | Access Waybinder configuration commands. |
| `/rtp reload` | Reload RTP configuration. |

## `/back` vs `/rtpback`

The two return commands intentionally track different things.

- `/back` is the general return workflow for previous Waybinder teleports and death locations.
- `/rtpback` remembers the **destination of the most recent successful `/rtp`**.
- Using `/home`, `/warp`, `/back`, or dying does not replace the saved RTP destination.
- Another successful `/rtp` replaces it.

For example: `Plains → /rtp → Taiga → /home → Plains → /rtpback → Taiga`.

## Requirements

**Required**

- Minecraft 26.3
- Fabric Loader 0.19.5 or newer
- Fabric API
- Java 25 or newer

**Recommended for the in-game settings screen**

- Mod Menu
- YetAnotherConfigLib (YACL) 3.9.7 or newer

Placeholder API is bundled as a runtime component and does not need to be installed separately.

## Configuration

Waybinder separates personal client preferences from server-controlled gameplay settings. Normal players can view server settings, while administrators can change them when permitted.

The config covers teleport delay/effects, homes, warps, TPA, `/back`, RTP radius and cooldowns, dimension policies, biome blacklists, ocean avoidance, search attempts, and safety checks.

See **[Configuration](docs/CONFIGURATION.md)** for a plain-English explanation of each group.

## Compatibility

Waybinder intentionally keeps the original Simple Warp TPA Home Back world-data location so existing homes and warps remain compatible.

Do not install standalone **Simple Warp TPA Home Back** or **FastRTP** alongside Waybinder; their functionality is already integrated and Waybinder marks them as incompatible to avoid duplicate commands.

## Credits

- **Kukiz** — Waybinder developer and maintainer.
- **ZiYun** — original home, TPA, warp, and return system from Simple Warp TPA Home Back.
- **Wesley1808** — FastRTP.
- **Placeholder API / Patbox** — bundled compatibility component used by the RTP implementation.

See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) for the full attribution and license information.

## License

Waybinder is released under the **MIT License**. Third-party components retain their own licenses; copies are included under [`LICENSES/`](LICENSES/).

## Development status

The public repository is being organized around the stable **1.2.0** release. Documentation, licensing, and project history are tracked here first; the complete buildable Gradle source tree will follow as the project files are cleaned up for public development.

Bug reports and feature ideas are welcome through GitHub Issues.
