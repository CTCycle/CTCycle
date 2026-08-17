# Profile README audit

Date: 2026-08-18

## Scope

- Audited the complete profile README, repository structure, existing Pages portfolio, recent README history, and public repository metadata.
- The current README had no live widgets. An older commit referenced the paused `github-readme-stats-beta-ten-32.vercel.app` instance.
- The canonical Trophy endpoint returned `402 DEPLOYMENT_DISABLED`; the canonical Readme Stats endpoint returned `503 DEPLOYMENT_PAUSED` during this audit.

## Implemented

- Reworked the README around a concise introduction, evidence-based selected work, current focus, toolchain, background, activity cards, achievements, and contact links.
- Added repository-owned stats, top-language, and light/dark Trophy SVGs under `profile/`.
- Added `.github/workflows/update-profile-cards.yml` with daily/manual refresh, `contents: write` permission, failure-on-error stats generation, and pinned generator commits.
- Kept the existing Pages portfolio link and project links; removed badge-heavy decoration, visitor counters, live public widget URLs, and duplicated activity visualizations.

## Validation evidence

- GitHub Markdown rendering endpoint accepted the README as GitHub Flavored Markdown and sanitized the tables, local images, and `<picture>` element successfully.
- Rendered DOM checks passed at 1440px and 390px widths with no horizontal overflow.
- All four local SVGs parse as XML, have nonzero dimensions, and contain no error/deployment placeholder text.
- Final README URL checks: GitHub project links, GitHub Profile Trophy, and GitHub Pages returned HTTP 200. LinkedIn returned HTTP 999 and Medium returned HTTP 403 from the automated client; both are remote access restrictions rather than confirmed broken destinations.
- Browser screenshot capture repeatedly timed out in the connected Chrome/CDP surface, so screenshot evidence is not claimed. DOM, image-load, and responsive-width checks were completed instead.

## Workflow sources

- `stats-organization/github-readme-stats-action` pinned to commit `e856fc8de9d7729b463c468911e232cfbdc3d55e` (the dereferenced `v2.0.2` tag), using GitHub Stats Extended `2.1.5`.
- Trophy refresh uses the upstream-listed `trophy.ryglcloud.net` mirror with `trophy.benkou.dev` fallback, preserving `username=CTCycle`, `theme`, `row=1`, `column=7`, `margin-w=12`, `no-bg=true`, and `no-frame=true`.
