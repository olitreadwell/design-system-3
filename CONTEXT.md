<!-- @license CC0-1.0 -->

# Amsterdam/design-system context
> refreshed 2026-09-04 | upstream default: develop @ e77c7d9f7ac

## Identity & policies
- upstream: Amsterdam/design-system, default branch `develop`, primary language TypeScript (pnpm monorepo: tokens, css, react, storybook). English-first: yes (docs, PRs, commits in English; some issue titles Dutch).
- CLA/DCO: none (no CLA bot, no DCO sign-off required).
- AI-assisted PR policy: unstated / allowed — AGENTS.md explicitly welcomes agents ("Human contributors and agents should both follow the conventions"). No AI ban, no AI disclosure required. Org default `.github` has only CODE_OF_CONDUCT, README, SECURITY — no AI policy.
- signed commits required: no.
- PR template: `.github/pull_request_template.md` (Links / What / Why / How / Checklist / Additional notes). Fill verbatim.
- external tracker: GitHub issues + internal Atlassian (DES-#### tickets referenced in branch names). CONTRIBUTING says non-Amsterdam contributors should contact maintainers; issue-first preferred for non-trivial changes.
- issue_first_required: true (CONTRIBUTING: "usually best to first open an issue to discuss the changes").

## Conventions (verified from merged PRs)
- branch naming: `type/DES-####-kebab-description` for maintainers; external-style branches use `type/kebab-description` (e.g. `feat/image-loading-background`, `chore/grid-medium-column-count`). Types: feat/fix/chore.
- commit style: English imperative mood, Conventional Commits PR titles (`feat(Scope): ...`, `fix(Scope): ...`, `chore: ...`). Squash-merge.
- test command: `pnpm test` (Vitest, packages/react); lint: `pnpm run lint` (ESLint + Stylelint + Prettier). Build: `pnpm run build`.
- CI: GitHub Actions + Chromatic visual regression. `/chromatic test` comment required for visual changes.
- outside merges: dependabot + maintainers; external contributor PRs are rare (CONTRIBUTING steers non-Amsterdam contributors to contact maintainers first).

## Maintainer picture
- active maintainers: Vincent Smedinga, Ruben Sibon (both commit daily). Responsive to issues (both #2897 and #2954 got maintainer replies within days).
- in-flight areas: Character Count docs, agent-instruction cleanup, release notes, Image Slider a11y (DES-987 backlog, #2954).

## Issue-area health
- #2954 (bug, Image Slider a11y): maintainer RubenSibon acknowledged, moved existing DES-987 ticket to top of backlog — CLAIMED territory, large component redesign. Avoid.
- #2897 (enhancement, overflow-wrap:anywhere): maintainer VincentSmedinga "looks promising, we'll look into it" — soft-acknowledged, global CSS change, likely claimed. Avoid.
- #1772: Dutch, old (2024), accessibility review — not actionable.
- No clean documented+approved+open issue survives → run repo-audit matrix for a verifiable self-found gap.

## Gap ledger (dedupe — READ FIRST, never re-pick)
- `2026-09-04` self-found dead links (docs dimension) — pr-opened (chore/fix-dead-links-in-docs) — 3 verified-404 links fixed in 4 files; deduped clean.

## Mined gaps (discovered, not yet attempted)
- `2026-09-04` docs: datasift.github.io/gitflow/IntroducingGitFlow.html returns 404 (curl -sSL -o /dev/null -w '%{http_code}' → 404; site root also 404) in CONTRIBUTING.md:56 + documentation/git.md:43 → replace with Atlassian GitFlow tutorial (200). Dedupe: issue 767 (closed 2023, "Change docs to new GitFlow setup") did not touch this link; no open/closed/merged PR touches it. status: attempted → pr-opened.
- `2026-09-04` docs: nldesignsystem.nl/handboek/developer/architectuur (no trailing slash) returns 404 in packages/css/README.md:32 → add trailing slash architectuur/ (200). Dedupe: no upstream issue/PR. status: attempted → pr-opened.
- `2026-09-04` docs: reactrouter.com/en/main/hooks/use-link-click-handler returns 404 in storybook/src/docs/guidelines/routing-libraries.docs.mdx:32 → replace with reactrouter.com/en/main/api/hooks/useLinkClickHandler (200, from reactrouter.com/en/main/hooks index). Dedupe: PR 2687 (merged) added the doc but did not fix the link; no other PR touches it. status: attempted → pr-opened.
