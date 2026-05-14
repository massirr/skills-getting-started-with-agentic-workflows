---
name: update-github-info
description: Draft website updates for Mona's GitHub Info site from official GitHub sources.
on:
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.com
    - github.blog
    - awesome-copilot.github.com
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before making changes.

Use these sources:
- `notes/mona-notes.md`
- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/
- Awesome Copilot workflows: https://awesome-copilot.github.com/workflows/

Web fetch https://awesome-copilot.github.com/workflows/ and include relevant workflows from that page as additional sources when drafting updates.

Update `site/content/github-info.md` with concise, practical updates for readers. Make sure the generated change updates the website content file directly and includes source context when content comes from the GitHub Blog, GitHub Changelog, or Awesome Copilot workflows.

Open a pull request for Mona to review and keep it open.
Use a pull request title that clearly mentions Mona or GitHub Info, such as `Update Mona website updater workflow`.
Do not write directly to `main`; rely on `safe-outputs` with `create-pull-request`.