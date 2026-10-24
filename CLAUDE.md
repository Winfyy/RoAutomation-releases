# Project memory

Shared memory for every Claude session working in this repo. Read it at the start of a session.
Update it whenever something worth remembering is decided or learned: keep entries short, dated,
and move stale ones to "Archive" instead of letting them pile up.

## About the user / project
- Builds Roblox games in Luau (simulator-style games, e.g. pets, eggs, mining).
- Wants code delivered directly, with minimal back-and-forth; prefers Claude to act without asking for routine steps.
- Game source code has not been added to this repo yet. When it is, run `/graphify .` on it and note the key systems below.

## Tooling (cloud environment)
The environment setup script installs these at session start:
- `graphify`: `/graphify .` builds a knowledge graph of the codebase; then `/graphify query|path|explain`.
- `rbx-check [paths]`: StyLua format check + Selene lint + luau-lsp type check against the Roblox API.
  Run it on every Luau file before handing code to the user.
- `stylua`, `selene`, `luau-lsp`, `luau`, `luau-analyze`, `lune`, `rojo`, `wally`.
- Roblox type definitions: `~/.local/share/roblox-types/globalTypes.d.luau`.

Environment notes:
- GitHub release downloads and `setup.rbxcdn.com` are blocked by the network policy; crates.io, PyPI, npm,
  `git clone` from GitHub and `raw.githubusercontent.com` work.
- Selene is built with `ureq` `native-certs` so it trusts the proxy CA; the crates.io build cannot fetch the Roblox std.
- luau-lsp must be built with Clang (GCC trips a `-Werror=maybe-uninitialized` false positive).

## Decisions
- 2026-10-24: Memory lives in this file, not in a looping helper session (cheaper, never fades).

## Game systems
_(empty: fill in once game code is in the repo)_

## Open tasks
- Add the Roblox game source to this repo (or attach its repo) so it can be graphed and checked.

## Archive
