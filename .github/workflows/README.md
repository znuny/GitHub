# Znuny GitHub Workflows

This directory contains reusable GitHub Actions workflows that can be used across all Znuny repositories.

## Overview

Reusable workflows allow you to avoid copying and pasting workflow code between repositories. They act as a template that can be referenced by other workflow files.

## How to Use

To use these reusable workflows in your repository, reference them in your workflow file using the following syntax:

```yaml
jobs:
  your-job-name:
    uses: znuny/GitHub/.github/workflows/workflow-name.yml@branch
```

## Available Workflows

### Stale Workflow (`stale.yml`)

A workflow that automatically identifies and manages stale issues and pull requests. It helps keep repositories clean by marking or closing issues and PRs that have had no recent activity.

Features:
- Automatically identifies inactive issues and pull requests
- Adds 'stale' labels to inactive items
- Can close items after extended inactivity
- Configurable through workflow parameters

```yaml
name: Stale

on:
  workflow_dispatch:      # Allows you to run this workflow manually from the Actions tab
  schedule:               # Allows you to run this workflow automatically
    - cron: '0 1 * * *'   # Runs at 01:00 UTC every day

jobs:
  Stale:
    uses: znuny/GitHub/.github/workflows/stale.yml@dev
```

---