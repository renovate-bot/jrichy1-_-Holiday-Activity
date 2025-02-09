Repository was created by [Working Copy](https://workingcopy.app/?ct=holiday) to decorate the GitHub Activity Overview.

## Dependency Dashboard

This repository uses Renovate to manage and update dependencies. Renovate helps to keep your dependencies up-to-date by automatically creating pull requests for updates.

### How to Use the Dependency Dashboard

1. **Check the Dashboard**: The dependency dashboard provides an overview of all the dependencies that need to be updated. You can find the dashboard in the [Issues](https://github.com/jrichy1/Holiday-Activity/issues) section of this repository.
2. **Review Pull Requests**: Renovate will automatically create pull requests for dependency updates. Review these pull requests to ensure that the updates do not break your code.
3. **Merge Pull Requests**: Once you have reviewed the pull requests and are confident that the updates are safe, merge them into the main branch.

### Configuration

The Renovate configuration is defined in the `renovate.json` file. Here is an example of the configuration:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": [
    "config:recommended"
  ],
  "dashboard": true,
  "labels": ["dependencies", "renovate", "update"]
}
```

### GitHub Actions Workflow

A GitHub Actions workflow is set up to run Renovate and update the dependency dashboard daily. The workflow file is located at `.github/workflows/renovate-dashboard.yml`. Here is an example of the workflow configuration:

```yaml
name: Renovate Dependency Dashboard

on:
  schedule:
    - cron: '0 0 * * *'

jobs:
  dashboard:
    runs-on: ubuntu-latest

    labels: ["renovate", "dashboard"]

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Run Renovate CLI
        run: npx renovate
```

The Renovate dependency dashboard has been triggered to run again on this repository. ✅

## Predefined Labeling System

This repository uses a predefined labeling system to categorize and manage issues, pull requests, and workflows. The following labels are used:

### Renovate Labels

- **dependencies**: Used for dependency updates.
- **renovate**: Used for Renovate-related tasks.
- **update**: Used for general updates.

### GitHub Actions Workflow Labels

- **ci**: Used for continuous integration workflows.
- **workflow**: Used for general workflow tasks.
- **codeql**: Used for CodeQL analysis workflows.
- **security**: Used for security-related workflows.
- **dashboard**: Used for the Renovate dependency dashboard workflow.
