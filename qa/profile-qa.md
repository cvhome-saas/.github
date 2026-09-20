# QA — the organisation profile

The README shown on https://github.com/cvhome-saas: what cvhome is, where to start reading, and the list of
repositories.

- **Scope** — the rendered profile and its links.
- **Runs on** — github.com, after the PR merges; the raw Markdown before.
- **Cases** — 3 (2 verified, 1 not verified)
- **Also see** — orchestrator `repos.yaml`, which the repository table mirrors.

## 00 — Before you start
Open https://github.com/cvhome-saas in a browser.

## 01 — Content
### 01.1 Every link resolves [verified]
- Steps: request every link in the file, following redirects, and check the status.
- Expect: each answers 200; no 404 on the docs site, every repository public.
- Result (2026-09-20, after the site deployed): all 25 answered 200. Ten documentation pages across the
  guide, architecture, guides, development and operations groups, and fifteen repository links.

### 01.2 The repository table matches the manifest [verified]
- Steps: compare the linked repository names with the `name:` entries in the orchestrator's `repos.yaml`.
- Expect: same set, nothing missing, nothing invented; `assets` marked retired.
- Result (2026-09-20): fifteen in the manifest, fifteen on the profile, no difference either way, and
  `assets` is marked retired.

### 01.3 The profile renders [not verified]
- Steps: view the organisation page.
- Expect: the two tables render as tables; no raw Markdown visible.

## REG — regression watchlist
- None.

## 99 — known gaps
- None. The docs-site links needed the site's rewrite merged and deployed, which happened on 2026-09-20.
