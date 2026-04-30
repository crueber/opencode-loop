# Changelog

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
