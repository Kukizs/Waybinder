# Changelog

All notable Waybinder changes are documented here.

## 1.2.0 — Minecraft 26.3

Waybinder 1.2.0 expands the original home/warp/TPA utility into a complete lightweight teleport mod with integrated random teleportation and a full in-game configuration experience.

### Added

- Integrated `/rtp` random teleportation directly into Waybinder.
- Added `/rtpback`, which returns to the destination of the most recent successful `/rtp`.
- Added configurable RTP radius, cooldown, dimension policy, ocean avoidance, biome restrictions, search attempts, and safety radius.
- Added a custom biome and biome-group blacklist editor with validation and pagination.
- Added `/tpahere` and typed TPA request handling.
- Added TPA request timeout, cooldown, and cross-dimension policies.
- Added server-authoritative configuration networking and permission-aware editing.
- Added personal client settings for chat closing and RTP coordinate display.
- Added Mod Menu + YACL configuration categories for General, Homes & Warps, TPA, Back, and RTP.
- Added custom About and Changelog screens.
- Added operator RTP cooldown-bypass control.

### Changed

- `/back` and `/rtpback` now intentionally track separate return workflows.
- Homes, warps, `/back`, and death no longer overwrite the saved RTP destination.
- RTP cooldown begins after a successful teleport rather than before it completes.
- `/back`, `/rtp`, and `/rtpback` follow the global teleport delay/effects settings.
- Home and warp systems can be enabled/disabled without deleting saved data.
- Home and warp limits can be changed live; lowering a limit does not delete existing entries.
- Home and warp overwrite behaviour is configurable.
- Setting descriptions and command feedback were rewritten for clarity.

### Fixed

- Multiple Minecraft 26.3 binary/API compatibility issues across Fabric, commands, components, dimensions, world loading, YACL, and RTP.
- Config Save flow that could trap the YACL screen.
- RTP safe-location checks on Minecraft 26.3.
- `/rtpback` crash caused by an outdated `BlockPos.containing(Vec3)` call.
- Operator cooldown behaviour so OP status alone no longer silently bypasses cooldown when the option is disabled.
- Enabling operator cooldown bypass during an active cooldown now takes effect immediately.
- Command Feedback is now actually respected by the relevant command confirmations.
- Old config permission gap in the server-authoritative config flow.

## 1.1.1 — Minecraft 26.3

### Changed

- Renamed `/swthbconfig` to `/waybinderconfig`.
- Renamed the RTP configuration file to `config/waybinder-rtp.json`.
- Renamed the old `/fastrtp` alias to `/waybinderrtp`, while keeping `/rtp` as the main command.
- Moved Waybinder assets into the `waybinder` namespace.
- Updated translation keys from `swthb.*` to `waybinder.*`.
- Cleaned up English home, warp, back, TPA, and RTP messages.
- Updated Waybinder logging names, mixin names, metadata, and release description.

### Licensing and compatibility

- Declared Waybinder's release license as MIT.
- Preserved the Simple Warp TPA Home Back CC0 notice.
- Preserved the FastRTP MIT notice and Wesley1808 attribution.
- Added the bundled Placeholder API LGPL-3.0 notice.
- Existing Simple Warp TPA Home Back home/warp world data remains compatible.

## 1.1.0 — Minecraft 26.3

- Integrated FastRTP directly into Waybinder as a single mod jar.
- Added `/rtp` and `/rtpback`.
- Kept `/back` separate from the RTP-specific return workflow.
- Added RTP cooldown, safe-position searching, dimension handling, and biome restriction support.
- Added `/rtp reload`.
- Added FastRTP licensing and attribution.
- Marked standalone Simple Warp TPA Home Back and FastRTP as incompatible.

## 1.0.0 — Minecraft 26.3

- Renamed the fork to **Waybinder**.
- Added `/setmainhome <name>` and `/clearmainhome`.
- Plain `/home` now teleports to the selected main home.
- `/homes` marks the selected home as `[Main]`.
- Main-home data persists with the world save.
- Converted the user-facing experience to English and cleaned up metadata.

---

## 1.2.0 development milestones

The following entries summarize the public 1.2.0 alpha development cycle. Minor failed UI experiments are intentionally omitted from the player-facing history where they did not change the final behaviour.

### 1.2.0-alpha.34 — Final polish

- Rewrote configuration descriptions so settings explain their exact behaviour, scope, defaults, and edge cases.
- Clarified RTP radius, cooldown, operator bypass, dimensions, biome restrictions, search attempts, and safety radius.
- Clarified TPA dimension policies, timeout, cooldown, and `/tpahere` behaviour.
- Clarified home/warp enable, limits, and overwrite behaviour.
- Polished About-screen wording and command feedback.

### 1.2.0-alpha.33 — About/Changelog navigation

- Added an **Open About** button to the Changelog screen.
- Added the custom About-screen redesign to the meaningful development changelog.

### 1.2.0-alpha.31 — About screen redesign

- Replaced the plain YACL About category with a custom Waybinder About screen.
- Added profile-style credit cards for Kukiz, ZiYun, Wesley1808, and Placeholder API.
- Added project history, Built With information, Changelog navigation, and a Waybinder-branded layout.

### 1.2.0-alpha.30 — Biome blacklist editor

- Finalized the custom biome blacklist editor.
- Added pagination for available biomes/groups and current blacklist entries.
- Added clear Back navigation.
- Typed values must match known biome or tag IDs; invalid arbitrary values are rejected.

### 1.2.0-alpha.24 — RTP return behaviour

- `/rtpback` now returns to the destination of the most recent successful `/rtp`.
- Homes, warps, `/back`, and death no longer replace the saved RTP destination.
- Another successful `/rtp` replaces the saved RTP destination.

### 1.2.0-alpha.23 — RTPBack compatibility fix

- Fixed a Minecraft 26.3 crash when using `/rtpback` caused by an outdated `BlockPos.containing(Vec3)` call.

### 1.2.0-alpha.22 — Teleport/settings fixes

- Wired Command Feedback into gameplay.
- Made `/back` follow the global Teleport Delay and Teleport Effects settings.
- Moved RTP cooldown start to the completed teleport.
- Made `/rtp` and `/rtpback` respect Teleport Effects.
- Aligned config-command limits with the GUI and fixed a config permission gap.

### 1.2.0-alpha.21 — Changelog navigation fix

- Fixed Back/Escape navigation from the custom Changelog screen by resetting the parent YACL placeholder tab before returning.

### 1.2.0-alpha.19 — Changelog scrolling

- Switched the Changelog to a native scroll area so long release history scrolls correctly.

### 1.2.0-alpha.17 — Custom Changelog screen

- Introduced the custom dark-panel Changelog screen with version headers and section styling.

### 1.2.0-alpha.15 — In-game changelog

- Added the first in-game Changelog category.

### 1.2.0-alpha.13 — Operator cooldown bypass fix

- Enabling Operators Bypass Cooldown during an active operator cooldown now immediately ignores/clears that timer.
- Disabling it means the next successful RTP starts the normal cooldown again.

### 1.2.0-alpha.12 — Operator cooldown control

- Added **Operators Bypass Cooldown** under RTP settings.
- The option defaults to OFF, so operators follow the normal cooldown unless explicitly enabled.
- Explicit Waybinder cooldown-bypass permission continues to bypass the cooldown independently.

### 1.2.0-alpha.11 — Config Save and biome UI

- Fixed the config Save flow that could leave the YACL screen stuck on "Save before exiting".
- Improved biome blacklist controls and presentation.

### 1.2.0-alpha.10 — Biome selection and RTP safety

- Added searchable biome selection to the blacklist UI.
- Fixed RTP safe-location checking for Minecraft 26.3.

### 1.2.0-alpha.9 — YACL compatibility

- Fixed the YACL `OptionDescription.of(Component...)` ABI mismatch.
- Improved config-screen error logging.

### 1.2.0-alpha.8 — Minecraft 26.3 compatibility

- Fixed text-component, dimension-command, RTP reload, and world-load API mismatches.

### 1.2.0-alpha.7 — Fabric compatibility hotfix

- Fixed a Fabric API binary-compatibility startup error in networking/client registration.

### 1.2.0-alpha.6 — In-game configuration

- Added Mod Menu integration and the YACL configuration screen.
- Added General, Homes & Warps, TPA, Back, RTP, and About categories.
- Added dependent-option disabling and real client preferences.
- Kept Mod Menu/YACL optional at runtime.

### 1.2.0-alpha.5 — Server-authoritative settings

- Added server-authoritative config networking.
- Added permission-aware admin editing, validation, atomic config application, and fresh snapshots on join.
- Added `config/waybinder-client.json` for personal client settings.

### 1.2.0-alpha.4 — RTP configuration rework

- Reworked RTP into Waybinder's config architecture.
- Added global teleport delay/cancellation support for RTP.
- Added radius, cooldown, dimension, ocean, blacklist, search-attempt, and safety settings.
- Preserved existing `config/waybinder-rtp.json` compatibility.

### 1.2.0-alpha.3 — TPA rework

- Added typed TPA/TPA_HERE requests and `/tpahere`.
- Added TPA enable, timeout, cooldown, and cross-dimension policies.
- Improved request replacement, expiry, and self-request handling.

### 1.2.0-alpha.2 — Home and warp settings

- Activated live enable/disable switches, overwrite controls, and configurable limits for homes and warps.
- Lowering limits no longer deletes existing entries.

### 1.2.0-alpha.1 — Config migration foundation

- Added config versioning and migration support.
- Preserved existing 1.1.1 homes, main homes, warps, settings, and legacy world-data paths.
- Added safer temporary-file/replace config writes.
