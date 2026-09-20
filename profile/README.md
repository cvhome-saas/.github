# cvhome

**cvhome** is an open-source, multi-tenant e-commerce platform you run in your own AWS account. One
platform layer serves many merchants; each store is a tenant inside a *pod*, a self-contained deployment of
the storefront and its services, so a platform can run a shared pool of stores or give one organisation a
pod of its own. Every store gets its own domain with certificates issued on demand.

- Java 25 / Spring Boot services, an Angular seller console, a Next.js storefront with themes, a Caddy edge.
- Deployed to ECS Fargate by a one-click CloudFormation bootstrap and Terraform.
- Runs on one machine with a single command, `lcl start`.

## Start here

| I want to | Read |
|---|---|
| understand what cvhome is and how it is shaped | [Introduction](https://cvhome-saas.github.io/guide/introduction) and [Core concepts](https://cvhome-saas.github.io/guide/core-concepts) |
| see the architecture at every level | [System context](https://cvhome-saas.github.io/architecture/system-context) and the pages that follow it |
| run it on my laptop | [Local development](https://cvhome-saas.github.io/development/local-development) |
| deploy it to my AWS account | [Deploy to AWS](https://cvhome-saas.github.io/operations/deployment-guide) |
| know what a merchant, a shopper or an operator sees | [Merchant journey](https://cvhome-saas.github.io/guides/merchant), [Shopper journey](https://cvhome-saas.github.io/guides/shopper), [Platform admin](https://cvhome-saas.github.io/guides/platform-admin) |
| contribute | [Contributing](https://cvhome-saas.github.io/development/contributing) |

## Repositories

| Repository | Kind | What it is |
|---|---|---|
| [cvhome](https://github.com/cvhome-saas/cvhome) | app | The application monorepo: Spring Boot services, the Angular console, the Next.js storefront. Source of truth for services and ports. |
| [cvhome-platform](https://github.com/cvhome-saas/cvhome-platform) | infra | Terraform and the CloudFormation bootstrap for ECS Fargate; the CodeBuild pipeline that builds and applies. |
| [lcl](https://github.com/cvhome-saas/lcl) | tool | The local stack runner, published to npm as `@cvhome-saas/lcl`. |
| [load-testing](https://github.com/cvhome-saas/load-testing) | tool | k6 load, stress, soak and browser suites, with the Prometheus and Grafana stack they report into. |
| [e2e-testing](https://github.com/cvhome-saas/e2e-testing) | tool | Playwright browser regression suite. |
| [saas-gateway](https://github.com/cvhome-saas/saas-gateway) | image | The Caddy image the pod edge is built from. |
| [caddy-domainlookup](https://github.com/cvhome-saas/caddy-domainlookup) | plugin | Caddy middleware that maps a request host to its store. |
| [certmagic-s3](https://github.com/cvhome-saas/certmagic-s3) | plugin | Caddy certificate storage in S3, so every edge task shares certificates. |
| [aws-otel-collector](https://github.com/cvhome-saas/aws-otel-collector) | image | The OpenTelemetry collector configuration for AWS environments. |
| [public-dkr](https://github.com/cvhome-saas/public-dkr) | mirror | Mirrors base images to the organisation's public ECR. |
| [cvhome-saas.github.io](https://github.com/cvhome-saas/cvhome-saas.github.io) | docs | This documentation site. |
| [ideation](https://github.com/cvhome-saas/ideation) | ideas | The product backlog as Markdown. |
| [orchestrator](https://github.com/cvhome-saas/orchestrator) | docs | The organisation root: repository manifest, cross-repo review, releases. |
| [assets](https://github.com/cvhome-saas/assets) | docs | Retired. Its `fast-run` install is replaced by lcl. |
| [.github](https://github.com/cvhome-saas/.github) | docs | This profile. |

Releases are cut in the orchestrator and tag every versioned repository with the same version; see
[Releases](https://cvhome-saas.github.io/operations/releases).
