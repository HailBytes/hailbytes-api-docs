# Contributing

## Check for existing work before you start

This repo has had recurring problems with duplicate pull requests: multiple
independent PRs implementing the same fix against the same file (see
[#34](https://github.com/HailBytes/hailbytes-api-docs/issues/34) — 27 open
PRs with ~9 duplicate/superseded submissions as of one audit). When two PRs
touch the same section of `asm/openapi.yaml`, `sat/openapi.yaml`, or
`docs/index.html`, whichever merges first puts the rest into conflict, and
reviewers end up evaluating several near-identical diffs instead of one.

Before opening a new issue or PR:

1. **Search open issues**: check whether the problem is already tracked.
2. **Search open PRs** touching the same file(s) — especially
   `asm/openapi.yaml`, `sat/openapi.yaml`, and `docs/index.html` — for a PR
   that already covers the same change.
3. If an open issue or PR already covers it, add to that thread (or review
   the existing PR) instead of starting a new, separate one.
4. If you find genuine duplicates while working, note them in your PR/issue
   description so a maintainer can close the redundant ones.

## Scope

Keep PRs focused on one change (one endpoint, one section, one bug) so they
review quickly and don't collide with other in-flight work on the same file.
