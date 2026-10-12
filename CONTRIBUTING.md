# Contributing to Waybinder

Thanks for helping improve Waybinder.

## Reporting bugs

Please use the Bug Report issue template and include:

- Waybinder version.
- Minecraft version.
- Fabric Loader and Fabric API versions.
- Whether the problem happens in singleplayer, on a dedicated server, or both.
- Clear steps to reproduce the issue.
- `latest.log` and a crash report when one exists.
- Screenshots when the problem is visual.

For teleport problems, include the exact command sequence you used. For config problems, mention which option was changed and whether the problem happened before or after saving/rejoining.

## Feature requests

Feature ideas are welcome. Please explain the problem the feature solves and how it would fit Waybinder's goal of being a lightweight teleport utility rather than a full server-management suite.

## Development

Waybinder targets Minecraft 26.3 on Fabric and requires Java 25 at runtime. The repository is currently being organized around the 1.2.0 stable release; build instructions will be expanded once the cleaned public Gradle source tree is available.

## Pull requests

Before opening a pull request:

1. Keep changes focused on one problem or feature.
2. Preserve backwards compatibility with existing Waybinder world data where practical.
3. Do not remove third-party attribution or license notices.
4. Test command behaviour and config-screen navigation relevant to your change.
5. Describe what you tested in the pull request body.
