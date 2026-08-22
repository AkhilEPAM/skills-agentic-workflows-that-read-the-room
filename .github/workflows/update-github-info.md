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
    allowed-paths:
      - site/content/github-info.md
network:
  allowed:
    - github.blog
    - github.com
safe-outputs:
  create-pull-request:
    title: "Update GitHub information"
    body: "Automated update proposed for Mona's review."
---

Read `notes/mona-notes.md` using GitHub repository API tools. Read relevant repository guidance and reference files using GitHub repository API tools, not terminal, CLI, or sandboxed commands.

Use web-fetch to read:
- https://github.blog/latest/
- https://github.blog/changelog/

Update `site/content/github-info.md` with accurate, relevant information. Open a pull request for Mona to review using the safe `create-pull-request` output. Do not modify the default branch directly.
