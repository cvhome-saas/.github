# QA — the organisation profile

The README shown on https://github.com/cvhome-saas: what cvhome is, where to start reading, and the list of
repositories.

- **Scope** — the rendered profile and its links.
- **Runs on** — github.com, after the PR merges; the raw Markdown before.
- **Cases** — 3 (0 verified, 3 not verified)
- **Also see** — orchestrator `repos.yaml`, which the repository table mirrors.

## 00 — Before you start
Open https://github.com/cvhome-saas in a browser.

## 01 — Content
### 01.1 Every link resolves [not verified]
- Steps: click every link in "Start here", every repository link, and the releases link.
- Expect: each opens the named page; no 404 on the docs site, every repository public.

### 01.2 The repository table matches the manifest [not verified]
- Steps: compare the table with `repos.yaml` in the orchestrator.
- Expect: same set of repositories, same kinds; `assets` marked retired.

### 01.3 The profile renders [not verified]
- Steps: view the organisation page.
- Expect: the two tables render as tables; no raw Markdown visible.

## REG — regression watchlist
- None.

## 99 — known gaps
- The docs-site links resolve only after the site's `docs/architecture-rewrite` PR has merged and deployed.
