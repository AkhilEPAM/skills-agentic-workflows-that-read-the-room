---
name: update-github-info
on:
  schedule: daily
  workflow_dispatch:
permissions:
  contents: read
tools:
  github:
    toolsets: [repos]
  web-fetch:
  edit:
network:
  allowed:
    - github.blog
    - github.com
safe-outputs:
  create-pull-request:
    reviewers: [Mona]
---

Read `notes/mona-notes.md` using GitHub repository API tools. Read relevant repository guidance and reference files using GitHub repository API tools, not terminal, CLI, or sandboxed commands.

Use web-fetch to read:
- https://github.blog/latest/
- https://github.blog/changelog/
- https://github.com/github/gh-aw/blob/main/.github/aw/github-agentic-workflows.md

Update `site/content/github-info.md` with accurate, relevant information. Open a pull request for Mona to review using the safe `create-pull-request` output. Do not modify the default branch directly.
