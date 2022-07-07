# Wipe Github Actions Cache

This action deletes *all* actions caches (created with [actions/cache](https://github.com/actions/cache))
attached to the current repository.

## Usage

### Example Workflow

```yaml
name: Clear all Github actions caches on sundays
on:
  schedule:
    - cron: "* * * * 0"
  workflow_dispatch:

jobs:
  my-job:
    name: Delete all caches
    runs-on: ubuntu-20.04

    steps:
      - name: Clear caches
        uses: uses: easimon/wipe-cache@main
        with:
          dry-run: 'true'
```

### Inputs

```yaml
  github-token:
    description: 'Your GITHUB_TOKEN.'
    required: false
    default: ${{ github.token }}
  dry-run:
    description: 'List caches only, do not clear them.'
    required: false
    default: 'false'
```
