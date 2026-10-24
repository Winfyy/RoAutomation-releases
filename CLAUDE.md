# Project memory

Shared memory for every Claude session working in this repo. Read it at the start of a session.
Update it whenever something worth remembering is decided or learned: keep entries short, dated,
and move stale ones to "Archive" instead of letting them pile up.

## About the user / project
- Builds Roblox games in Luau (simulator-style games, e.g. pets, eggs, mining).
- Wants code delivered directly, with minimal back-and-forth; prefers Claude to act without asking for routine steps.
- The games live on the user's PC, not in this repo: Obsidian vault `C:\Users\bbabo\Documents\Obsidian Vault`
  (Egg Heist = current focus; Geode Delve in `Roblox Game Prototype/`). RoAutomation app source: `C:\Users\bbabo\Documents\Codex\RoAutomation-dev`.
- A team of ~40 helper sessions runs on the PC (bridge environments "YounosPC"). The lead is the session titled
  "Geode Delve gamepad support" (session_01PCsqUd4pmfPRiXWPVsyRyu). The cloud session that set this file up acts as overseer.
- The user wants blunt, honest assessments, not agreement.

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
- 2026-10-24: Lead froze all work for ~6h after a declined permission prompt (Xbox Game Bar covered Studio during run 8).
  Told it to resume. Lesson: a denied tool means ask the user, not stop everything.
- 2026-10-24: Cost cuts. Geode Delve build loop (scheduled task) paused: it was producing nothing. Vault loop and game-critic
  loop told to run every 60 min (were 10 min). Critic under feature freeze: bugs/blockers only until Studio run 8 passes
  and the user playtests.
- 2026-10-24: Recommended focusing on Egg Heist; Geode Delve stays paused until Egg Heist ships (user's call).
- 2026-10-24: Plugins reviewed: install CodeBurn (token usage dashboard) on the PC; skip Caveman, LLM Council, Karpathy
  CLAUDE.md, GSD, Claude Octopus; I Have ADHD optional.
- 2026-10-24: Hourly "Helper watcher hourly" scheduled task (fresh cloud session, read-only) pushes a phone notification
  when PC sessions are stuck. The overseer session is trusted-device-only, so scheduled check-ins into it fail.

## Game systems
_(empty: fill in once game code is in the repo)_

## Open tasks
- Lead: resume Egg Heist Studio run 8; fix the 30-minute resume task bug (it counts helpers' log entries as the lead's).
- RoAutomation: fix wrong Gemini "used up until 28 Oct" detection (user's Gemini usage was 0% current / 25% weekly),
  confirm E6/E7 closed, finish promo videos + E13, then publish the release after v1.9.0 here.
- Waiting on the user: approve PowerShell prompts on PC helpers; import the 13 models into Studio; create badges on Roblox;
  pick icon (v4 vs 3 alternates); Invite a friend yes/no; phone test; public game name.

## Archive
