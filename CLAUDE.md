# Project memory

Shared memory for every Claude session working in this repo. Read it at the start of a session.
Update it whenever something worth remembering is decided or learned: keep entries short, dated,
and move stale ones to "Archive" instead of letting them pile up.

## About the user / project
- Builds Roblox games in Luau (simulator-style games, e.g. pets, eggs, mining).
- Wants code delivered directly, with minimal back-and-forth; prefers Claude to act without asking for routine steps.
- The games live on the user's PC, not in this repo: Obsidian vault `C:\Users\bbabo\Documents\Obsidian Vault`
  (Egg Heist = current focus; Geode Delve in `Roblox Game Prototype/`). RoAutomation app source: `C:\Users\bbabo\Documents\Codex\RoAutomation-dev`.
- A team of ~25 active helper sessions runs on the PC (bridge environments "YounosPC"). The lead is
  "★ LEAD · Egg Heist + RoAutomation" (session_01PCsqUd4pmfPRiXWPVsyRyu, formerly "Geode Delve gamepad support").
  The overseer is "★ OVERSEER · cloud" (session_01Ex8Lfq7aiRHzp81QB5k8Yp).
- Session naming (2026-10-24): prefix = area. EH · Egg Heist, RA · RoAutomation, VAULT · Obsidian vault upkeep,
  REVIEW · reviewers, GD · Geode Delve (paused). Keep new sessions on this scheme; archive finished one-off helpers.
- The user wants blunt, honest assessments, not agreement.
- HARD RULE for anything that controls the PC screen: never close, minimise, move or click anything on the SECOND
  monitor; all computer-use work happens on the FIRST monitor. If a needed window is on monitor 2, ask the user to move it.

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
- 2026-10-24: "Helper watcher hourly" scheduled task created but DISABLED: tasks created from the overseer session get no
  connectors, so it can't read sessions. User must add the Claude Code Remote connector in claude.ai scheduled tasks and
  enable it. The overseer session is trusted-device-only, so scheduled check-ins into it fail.
- 2026-10-24: Xbox Game Bar capture/popups disabled via HKCU registry (GameDVR_Enabled, AppCaptureEnabled,
  ShowStartupPanel = 0). Controller-button setting and never-sleep-on-AC were already set, so sleep did not cause stalls.

- 2026-10-24: G24M2020G is the user's SECOND monitor (they watch video there). Studio and all screen work go on
  the first monitor.
- 2026-10-24: User said "do it all for me", so the overseer decided: icon = v4; no Invite a friend in MVP; badge code stays
  with ids 0 and badge creation waits for publishing; top shortlist sound per cue as placeholder (user can swap by ear);
  working name "Egg Heist". Lead told to start Studio run 8 and fix the resume task.

## Game systems
_(empty: fill in once game code is in the repo)_

## Open tasks
- Lead: resume Egg Heist Studio run 8; fix the 30-minute resume task bug (it counts helpers' log entries as the lead's).
- RoAutomation: fix wrong Gemini "used up until 28 Oct" detection (user's Gemini usage was 0% current / 25% weekly),
  confirm E6/E7 closed, finish promo videos + E13, then publish the release after v1.9.0 here.
- Waiting on the user: approve PowerShell prompts on PC helpers; upload models/assets to their Roblox account;
  create badges once published; phone test; playtest after run 8; public game name.

## Archive
