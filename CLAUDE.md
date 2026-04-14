# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

`first-contributions` is a **tutorial repository**, not a software project. It has no source code, build system, tests, lint config, or package manager. All content is Markdown. The "contribution" performed by beginners is literally adding a line with their name to `Contributors.md` — the repository exists so newcomers can rehearse the fork → clone → edit → PR workflow against a live upstream.

## Auto-merge bot — critical to understand

`.github/workflows/auto-pr-merge.yml` runs on every `pull_request_target` touching `Contributors.md` and will **auto-merge (squash)** a PR only when BOTH conditions hold:

1. The PR changes **only** `Contributors.md` (no other files in the diff — the workflow string-compares the space-joined filename list to exactly `"Contributors.md"`).
2. The diff is either `+1/-0` or `+2/-1` lines (a pure append, or a one-line edit).

Anything else (touching translations, docs, README, multi-line edits) falls through to a bot comment that pings maintainers for human review. When evaluating or modifying contributor PRs, check these two conditions first — they determine whether the PR auto-merges or needs review.

On successful auto-merge the workflow posts a congratulations comment with a random celebration gif and social-share links. On merge conflict (HTTP 405 "not mergeable") it posts a link to `docs/additional-material/git_workflow_scenarios/resolving-merge-conflicts.md`.

## Repository layout

- `README.md` — the canonical English tutorial. **Source of truth** for every translation.
- `Contributors.md` — append-only list of contributors. Frequently malformed by beginners (missing leading `-`, stray brackets, wrong indent, duplicate entries, broken links). Expect messy diffs.
- `docs/translations/README.<lang>.md` — 100+ language translations of `README.md`. Per `.github/CONTRIBUTING.md`, all translations should mirror the English README's content exactly *except* for the language-switcher link block at the top (that diverges intentionally). When editing translations, request review from the listed reviewer(s) for that language in `.github/CONTRIBUTING.md`.
- `docs/cli-tool-tutorials/` — localized CLI walkthroughs (one file per language).
- `docs/gui-tool-tutorials/` — one file per GUI tool (GitHub Desktop, VS Code, IntelliJ, GitKraken, Sourcetree, Sublime Merge, VS 2017).
- `docs/additional-material/` — deeper git scenarios (merge conflicts, etc.), also translated.
- `.github/CONTRIBUTING.md` — **not** the beginner tutorial; this is the maintainer-facing guide and holds the per-language reviewer table.

## Common tasks

There is nothing to build, test, or lint — markdown only. Verify changes by reading the rendered file on GitHub or with a local markdown previewer.

- Adding a contributor: append a single `- [Name](https://github.com/username)` line anywhere in the middle of `Contributors.md`. Anything that keeps the diff to `+1/-0` or `+2/-1` and touches only this file will auto-merge.
- Editing translations: change only `docs/translations/README.<lang>.md`; keep the translation's language-switcher block intact; content should match the current English `README.md`.
- Updating the tutorial: changes to `README.md` should be propagated to all translations — flag this scope explicitly when proposing such a change, since it fans out to 100+ files and will not auto-merge.
