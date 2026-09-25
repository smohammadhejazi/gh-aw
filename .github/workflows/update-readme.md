---
on:
  push:
    branches: [main]
    paths-ignore:
      - "README.md"
permissions:
  contents: read
engine:
  id: codex
  model: openai/gpt-5-mini
safe-outputs:
  create-pull-request:
    title-prefix: "[readme] "
    labels: [automation]
    draft: false
---

# Update README with Latest Changes

Look at the most recent commit(s) just pushed to this repository
(`git log -3 --stat` and `git diff HEAD~1 HEAD` will show you what changed).

Update `README.md`:
- Add a "## Latest Changes" section near the top if it doesn't exist yet.
- Replace its content with 1–3 short, plain-language sentences summarizing
  what this push changed.
- Leave the rest of the README untouched.
