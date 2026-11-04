# Cloud report: fish-shell

- Upstream repo: https://github.com/fish-shell/fish-shell (default branch `master`)
- Upstream commit checked: `d92ccd4f8f6f08cfc8a0d9fa17333153e2922af1` ("Convert a completion `BTreeMap` to a `HashMap`", 2026-11-03)
- Fork: https://github.com/b84330808/fish-shell
- Date: 2026-11-04

## Result: STOPPED at step 2. Upstream bans AI-assisted contributions

No bug was investigated and no fix branch was created. Upstream's
`CONTRIBUTING.rst` bans contributions made with generative AI tools, and
this whole workflow runs in an AI coding assistant. Any PR it produced
would break that policy.

The policy, quoted verbatim from `CONTRIBUTING.rst` (lines 593-600 at `d92ccd4f8`):

> AI Contributions Policy
> =======================
>
> We do not accept contributions created with generative artificial intelligence tools.
> Do not submit pull requests, GitHub issues or comments, artwork,
> where the output has been created by or edited with one of these tools.
>
> This includes products such as GitHub Copilot, Zed AI, Cursor.dev's AI features, other coding assistants, and ChatGPT.

The ban covers more than PRs. It also covers GitHub issues and comments
whose content was "created by or edited with" such a tool. So the AI-made
text in this report should not be filed upstream as an issue or comment
either.

## Fix branches

None.

| Branch | SHA | Status |
|---|---|---|
| — | — | Not created: upstream's AI-contribution ban (see above) |

## Competing PR search

Not done, because no bug was picked.

## Policy notes (recorded for completeness)

- **AI policy:** contributions made with generative AI are banned (see above).
- **AGENTS.md / CLAUDE.md / Copilot instructions:** none in the repo. The
  only file with "claude" in its name is `share/completions/claude.fish`, a
  shell completion script, not instructions.
- **Text aimed at AI agents:** the only such text is the AI Contributions
  Policy above. It is recorded here and was obeyed by stopping, which is
  also what this task's step 2 says to do.
- **CLA / DCO:** neither one. `CONTRIBUTING.rst`, `.github/` and the
  workflows never mention `Signed-off-by`, DCO or a CLA. The license is GPLv2.
- **PR template** (`.github/PULL_REQUEST_TEMPLATE.md`): a TODO checklist:
  - commit message mentions `Fixes issue #<n>` when addressing an issue
  - user docs/manpages updated for usage changes
  - tests added for fixed regressions
  - `CHANGELOG.rst` updated for user-visible changes (usually skipped for completions)
- **Other contribution rules:**
  - linear "recipe-style" history: no fixup commits, rewrite and rebase instead
  - every commit must pass `cargo xtask check`
  - add `Fixes #<n>` at the end of the commit description
  - format with `cargo xtask format`
  - keep to the MSRV, which is the `rustc` in Debian Stable
  - patches can also go to `~krobelus/fish-shell@lists.sr.ht`
- **Tests:**
  - Rust unit tests: `cargo test`
  - system tests: `tests/test_driver.py target/debug [tests/checks/<file>.fish]`
  - interactive tests: `tests/pexpects`
- **Security:** `SECURITY.md` asks for private vulnerability reports. Nothing
  security-related was found, since no code was investigated.

## Suggested follow-up

Skip fish-shell for AI-assisted contribution work. If Wei-Lun Li wants to
contribute here, it has to be written by hand without AI tools, as the
policy requires.

_This report was written by an autonomous Claude Code cloud session and pushed only to the fork._
