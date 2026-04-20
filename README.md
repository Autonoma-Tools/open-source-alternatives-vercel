# Open-Source Vercel Alternatives: Coolify, Dokku, Kamal, and CapRover Compared

Companion code for the Autonoma blog post 'Open-Source Vercel Alternatives: Coolify, Dokku, Kamal, and CapRover Compared'. This repo provides a GitHub Actions workflow that runs Autonoma E2E tests against the preview URL produced by your self-hosted PaaS (Coolify, Dokku, Kamal, or CapRover) on every pull request, polls the Autonoma API for results, and posts a pass/fail status comment back to the PR.

> Companion code for the Autonoma blog post: **[Open-Source Vercel Alternatives: Coolify, Dokku, Kamal, and CapRover Compared](https://getautonoma.com/blog/open-source-alternatives-vercel)**

## Requirements

A GitHub repository with Actions enabled, a self-hosted PaaS (Coolify, Dokku, Kamal, or CapRover) that produces a reachable preview URL per pull request, and an Autonoma account with a project API key.

## Quickstart

```bash
git clone https://github.com/Autonoma-Tools/open-source-alternatives-vercel.git
cd open-source-alternatives-vercel
1. Copy .github/workflows/preview-test.yml into your repo's .github/workflows/ directory.
2. Add AUTONOMA_API_KEY and AUTONOMA_PROJECT_ID as GitHub Actions secrets.
3. Edit the 'Resolve preview URL' step and uncomment the block that matches your self-hosted PaaS (Coolify, Dokku, Kamal, or CapRover) — or dispatch the workflow via repository_dispatch with a preview_url payload from your PaaS webhook.
4. Open a pull request. The workflow runs after each deploy, triggers Autonoma E2E tests against the preview URL, polls until the run completes, and comments the result on the PR.
```

## Project structure

```
.
├── .github/
│   └── workflows/
│       └── preview-test.yml
├── .gitignore
├── LICENSE
└── README.md
```

- `.github/workflows/` — the GitHub Actions workflow that triggers Autonoma E2E runs against a self-hosted preview URL and posts results back to the pull request.

## About

This repository is maintained by [Autonoma](https://getautonoma.com) as reference material for the linked blog post. Autonoma builds autonomous AI agents that plan, execute, and maintain end-to-end tests directly from your codebase.

If something here is wrong, out of date, or unclear, please [open an issue](https://github.com/Autonoma-Tools/open-source-alternatives-vercel/issues/new).

## License

Released under the [MIT License](./LICENSE) © 2026 Autonoma Labs.
