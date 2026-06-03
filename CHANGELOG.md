# Changelog

## 0.5.6

- Added clearer README examples for prompt loops, scheduled question loops, OpenCode slash-command loops, shell loops, first-run timing, and idle-safe behavior.
- Stabilized `/loop-command 200m /compact` by routing `/compact` and `/summarize` through OpenCode TUI compact handling instead of treating them as custom prompt commands.
- Clarified that command loops wait for idle and should be used for slash commands such as `/compact`.
- Kept fallback compatibility with older SDK-style calls where possible.

## 0.5.5

- Added explicit loop action types for prompt loops, scheduled question/check loops, OpenCode slash-command loops, and shell-command loops.
- Added `/loop-command` and `/loop-cmd` for scheduled OpenCode commands such as `/compact`. These wait for the first interval by default and run only when OpenCode is idle.
- Added `/loop-ask` for recurring check prompts such as “did you run tests, tsc --noEmit, and build?” It waits for the first interval by default.
- Added `/loop-prompt` to force prompt mode.
- Added `/loop-shell` for recurring shell commands.
- Added `/loop` type flags: `--prompt`, `--ask`, `--command`, `--cmd`, `--slash`, `--shell`, and `--compact`.
- Clarified README examples for scheduled `/compact`, hourly quality checks, and idle-safe timing.
- Added `publishConfig.access=public` and normalized npm bin paths.

## 0.5.4

- Fixed compatibility with recent OpenCode SDK/TUI call shapes.
- Updated session prompt, shell, and toast calls for current OpenCode while keeping backwards-compatible fallbacks.
- Added `session.status` idle gating and debounce so loop runs wait for OpenCode to become idle and do not stack on busy/queued turns.
- Improved runtime logging for prompt/shell/toast failures.
- Fixed the known update-related symptoms where `/loop` could appear queued, stay at `runs=0`, or only work intermittently after OpenCode updates.

## 0.5.0

- Added `opencode-loopd` background daemon for long-running loops outside the OpenCode TUI.
- Added `opencode-loopd install-task` and `opencode-loopd uninstall-task` helpers for Windows Task Scheduler.
- Updated README to clearly explain the difference between session-bound TUI loops and background daemon loops.
- Added npm bin entry for `opencode-loopd`.
- Updated package check script to validate the daemon script.

## 0.4.4

- Made the npm install path the primary README installation method now that the package is published as `@bybrawe/opencode-loop`.
- Clarified that `npx -y @bybrawe/opencode-loop` installs both the plugin file and `/loop-*` command markdown files.
- Moved the OpenCode `plugin` array config to an optional/advanced section because config-only loading may not install slash command markdown files.
- Removed maintainer/publish-oriented instructions from the user-facing install flow.


## 0.4.3

- Fixed duplicate loop creation by making /loop replace/upsert the default loop instead of appending duplicate jobs.
- Added --multi for users who intentionally want multiple independent loops in one session.
- Added --replace as an explicit alias for the default upsert behavior.
- Made command markdown files no-op/silent so the model is less likely to explain the command or create scheduler files.
- Hardened the continuation prompt to avoid scheduling, documentation search, and command explanation loops.
- Clarified that the plugin is session/TUI-bound and does not keep running after OpenCode, the terminal, or the machine disconnects.

## 0.4.2

- Changed npm package name to scoped package `@bybrawe/opencode-loop`.
- Fixed README npm/OpenCode config examples to use `"plugin": ["@bybrawe/opencode-loop"]`.
- Added an npm `bin` installer so `npx -y @bybrawe/opencode-loop` can copy plugin and command files into the OpenCode config directory.
- Clarified that `opencode-loop` and `@bybrawe/opencode-loop` are different npm package names.

## 0.4.1

- Fixed installation docs for GitHub/local installs.
- Clarified that `plugin`: [`opencode-loop`] only works after npm publishing.
- Added manual global install and project-local install instructions.
- Added verification and troubleshooting steps for `/loop-help` and `/loop-doctor`.

## 0.4.0

- Public repository metadata updated for `ByBrawe/opencode-loop`.
- Package renamed to `opencode-loop`.
- README rewritten in English for public GitHub discovery and SEO.
- Added `--prompt-file` for long reusable prompts.
- Added `--include-file` for extra context files.
- Added `--max-runtime` for total runtime limits.
- Added `--max-failures` and `--pause-on-verify-fail` for failure control.
- Added `--postrun` and `--notify` hooks.
- Added `--dry-run` preview mode.
- Added `/loop-doctor`, `/loop-init`, and `/loop-export` commands.
- Improved max-runs finalization so the final run can still verify/checkpoint.
- Improved state cleanup for non-assistant actions such as `/compact`.
- Kept all examples project-neutral and English.

## 0.3.1

- Converted public examples to English.
- Removed private/project-specific language from README.
- Added public `progress.md` workflow examples.

## 0.3.0

- Added SEO-oriented README for OpenCode loop / Claude Code style loop use cases.
- Added `/loop-help` and `/loop-logs`.
- Added `--verify`, `--preflight`, `--stop-file`, and `--progress-file`.

## 0.2.0

- Added max runs, timeout, until, compact scheduling, tests, checkpoints, branch setup, safe mode, batch mode, quiet mode, ask-never mode, watch mode, and preset commands.

## 0.1.0

- Initial local OpenCode loop plugin.
