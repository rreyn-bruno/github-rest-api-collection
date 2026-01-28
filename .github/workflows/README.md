# GitHub Actions Workflow

## Bruno API Tests Workflow

This workflow automatically runs the Bruno API test collection against the GitHub REST API.

### Triggers

The workflow runs on:

1. **Push events** - When code is pushed to `main` or `master` branches
2. **Pull requests** - When PRs are opened against `main` or `master`
3. **Scheduled** - Daily at 9:00 AM UTC (catches breaking API changes)
4. **Manual** - Can be triggered manually from the Actions tab

### What It Does

1. **Checks out the repository** - Gets the latest code
2. **Sets up Node.js** - Installs Node.js v20
3. **Installs Bruno CLI** - Installs `@usebruno/cli` globally
4. **Runs tests** - Executes all Bruno requests with tests
5. **Generates reports** - Creates JSON and JUnit XML reports
6. **Uploads artifacts** - Saves test results for 30 days
7. **Publishes results** - Shows test summary in the Actions UI

### Viewing Results

**In GitHub Actions UI:**
- Go to the "Actions" tab
- Click on a workflow run
- View the test summary and details
- Download artifacts for detailed results

**Test Artifacts:**
- `bruno-test-results` - Contains JSON output of all test runs
- `test-results/*.xml` - JUnit XML format for CI integration

### Customization

**Change schedule:**
Edit the cron expression in `bruno-tests.yml`:
```yaml
schedule:
  - cron: '0 9 * * *'  # Daily at 9 AM UTC
```

**Add environment variables:**
If you need GitHub API tokens or other secrets:
```yaml
- name: Run Bruno tests
  run: bru run --env Github
  env:
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

**Change Node.js version:**
```yaml
- name: Setup Node.js
  uses: actions/setup-node@v4
  with:
    node-version: '20'  # Change to desired version
```

### Troubleshooting

**Tests failing?**
- Check if GitHub API is accessible
- Verify the Bruno CLI version is compatible
- Review test assertions in `.bru` files
- Check rate limiting (GitHub API has limits)

**Workflow not running?**
- Ensure Actions are enabled in repository settings
- Check branch names match the workflow triggers
- Verify the workflow file is in `.github/workflows/`

