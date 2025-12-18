# hack_js

Scan JavaScript dependencies for known security vulnerabilities using `npm audit`.

This action **fails the workflow** when **moderate or higher** vulnerabilities are found, making it suitable for **blocking pull request merges** using GitHub repo rulesets.

---

## Inputs

| Name           | Required | Description                 |
| -------------- | -------- | --------------------------- |
| `node_version` | Yes      | Node.js version (e.g. `18`) |
| `GITHUB_TOKEN` | Yes      | GitHub token                |

---

## Usage

```yaml
name: Dependency Audit

on:
  pull_request:
  push:
    branches: [main]

jobs:
  audit:
    runs-on: ubuntu-latest
    steps:
      - uses: PocAccount2/hack_js@v2
        with:
          node_version: '18'
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

