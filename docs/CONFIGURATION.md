# Waybinder configuration

Waybinder's gameplay settings are controlled by the current world/server. Players may view them, while administrators can edit them when they have permission. Personal client preferences only affect the local player.

## General

### Teleport Delay

How long Waybinder waits before completing `/home`, `/warp`, TPA, `/back`, `/rtp`, and `/rtpback` teleports. `0` seconds means instant. Moving during the countdown cancels the teleport.

### Teleport Effects

Plays portal particles and an Enderman teleport sound when a Waybinder teleport completes. Disable it to remove those arrival effects.

### Command Feedback

Shows routine success messages for homes, warps, `/back`, and RTP. Turning it off hides those confirmations only; errors, warnings, lists, TPA requests, and teleport countdowns still appear.

### Close Chat After Commands

A personal client option. Automatically closes chat after supported clickable Waybinder actions, such as clicking a home or a TPA Accept/Deny button. Commands typed normally are unaffected.

### Show Teleport Coordinates

A personal client option. Shows destination coordinates and the dimension after a successful `/rtp`. Disable it for a simpler completion message.

## Homes

### Homes Enabled

Master switch for `/sethome`, `/home`, `/homes`, `/delhome`, and the main-home commands. Disabling homes does not delete saved home data.

### Maximum Homes

Maximum number of homes each player may have. Lowering the limit does not delete existing homes; players already above the new limit simply cannot create more until they are below it.

### Allow Home Overwrite

When enabled, using `/sethome <name>` on an existing name moves that home to the player's current position. When disabled, the old home must be deleted first.

## Public Warps

### Public Warps Enabled

Master switch for `/warp`, `/warps`, `/setwarp`, and `/delwarp`. Disabling public warps does not delete saved warp data.

### Maximum Public Warps

Maximum number of public warps stored by the server. Lowering the limit does not delete existing warps; new ones cannot be created until the total is below the new limit.

### Allow Warp Overwrite

When enabled, `/setwarp <name>` can move an existing public warp with the same name. When disabled, that warp must be deleted first.

## TPA

### TPA Enabled

Master switch for player teleport requests. Disables `/tpa`, `/tpaccept`, and `/tpdeny`; `/tpahere` is also unavailable while TPA is disabled.

### Request Timeout

How long an unanswered teleport request remains valid before it expires.

### TPA Cooldown

How long a player must wait after sending a valid teleport request before sending another one. `0` seconds disables the cooldown.

### Cross-Dimension TPA

- **Same Dimension Only** — blocks every cross-dimension request.
- **Overworld + Nether** — allows requests between the Overworld and Nether.
- **All Dimensions** — allows any available dimension.

### Allow `/tpahere`

Allows `/tpahere <player>`, which asks the other player to teleport to the requester. Normal `/tpa` requests work independently of this option.

## Back

### `/back` Enabled

Enables the general `/back` return point. It can represent a player's position before a Waybinder teleport or their death location. Disabling `/back` does not erase the saved point.

## RTP

### RTP Enabled

Master switch for `/rtp`.

### Minimum Radius

Closest distance in blocks that `/rtp` may choose from the current dimension's world-border centre, normally `0, 0`. It cannot be greater than Maximum Radius.

### Maximum Radius

Farthest distance in blocks that `/rtp` may choose from the world-border centre. The world border can automatically reduce this limit.

### RTP Cooldown

How long a player must wait after a successful `/rtp` before using `/rtp` again. `0` seconds disables the cooldown.

### Operators Bypass Cooldown

When enabled, server operators ignore the RTP cooldown. When disabled, operators follow the same cooldown as everyone else. A player with the explicit Waybinder cooldown-bypass permission still bypasses it.

### `/rtpback` Enabled

Enables `/rtpback`, which returns a player to the destination of their most recent successful `/rtp`. Homes, warps, `/back`, and death do not replace this saved RTP destination.

### Allowed Dimensions

- **Overworld** — `/rtp` always uses the Overworld.
- **Overworld + Nether** — Nether players stay in the Nether; players elsewhere use the Overworld.
- **All Dimensions** — RTP stays in the player's current dimension.

### Avoid Oceans

Separately rejects ocean, deep-ocean, river, and beach biome groups during `/rtp`. These groups do not also need to be added to the custom blacklists.

### Avoid Blacklisted Biomes

When enabled, RTP respects both custom lists below. Turning it off ignores the lists without deleting them.

### Biome Blacklist (Specific Biomes)

Blocks individual exact biomes. For example, blacklisting Plains blocks Plains only.

### Biome Tag Blacklist (Biome Groups)

Blocks whole groups of related biomes using biome tags. This is useful when several biome variants should all be excluded at once.

### Maximum Search Attempts

Maximum number of candidate locations `/rtp` checks before giving up. Higher values can improve success when many locations are unsafe or blacklisted, but can increase server work.

### Safety Check Radius

How far around a candidate landing spot Waybinder checks for dangerous blocks. Larger values are stricter and can make RTP searches take longer.
