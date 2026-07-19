# Contributing

## Before you start: check for existing work

This repo has repeatedly ended up with multiple open PRs independently
implementing the same fix against the same file (see
[#34](https://github.com/HailBytes/hailbytes-api-docs/issues/34) for a
concrete example: 27 open PRs, ~9 of them duplicates or already superseded
by `main`). Duplicate work costs reviewer time and produces PRs that
conflict with each other the moment one of them merges.

Before opening an issue or PR — especially anything touching
`asm/openapi.yaml`, `sat/openapi.yaml`, or `docs/index.html` — check
whether the same change is already in flight:

1. **Search open issues**: `gh issue list --repo HailBytes/hailbytes-api-docs --state open`
2. **Search open PRs**: `gh pr list --repo HailBytes/hailbytes-api-docs --state open`
3. If an open issue or PR already covers the change you're about to make,
   don't start a new one. Either contribute to the existing PR, or comment
   on the issue instead.
4. If you find truly duplicate/overlapping open PRs while doing this,
   flag it (comment linking the duplicates) rather than adding another one
   to the pile.

## Making a change

1. Create a branch from `main`.
2. Keep the change scoped to what you're actually fixing — avoid bundling
   unrelated cleanups into the same PR, since that makes duplicate
   detection and review harder for everyone else.
3. If you're touching `asm/openapi.yaml` or `sat/openapi.yaml`, run
   Spectral locally before pushing:
   ```bash
   npx @stoplight/spectral-cli@6.16.0 lint asm/openapi.yaml --ruleset .spectral.yaml --fail-severity error
   npx @stoplight/spectral-cli@6.16.0 lint sat/openapi.yaml --ruleset .spectral.yaml --fail-severity error
   ```
4. Open a PR against `main`. The PR template includes a checklist item
   confirming you did the duplicate check above.
