## Github Rest API Collection

This collection lets you get used to Bruno by querying the `Repository` and `User` endpoints in Github. 

Clone the repo or click the button below to automatically open it in Bruno! 

[<img src="https://fetch.usebruno.com/button.svg" alt="Fetch in Bruno" style="width: 130px; height: 30px;" width="128" height="32">](https://fetch.usebruno.com?url=https%3A%2F%2Fgithub.com%2Fbruno-collections%2Fgithub-rest-api-collection.git "target=_blank rel=noopener noreferrer")
### Usage
```bash
# Clone this repo
git clone https://github.com/bruno-collections/github-rest-api-collection.git

# open the folder in bruno
# enjoy !!!
```

## Running Tests

This collection includes comprehensive tests for all API endpoints.

### Run Tests Locally

**Option 1: Using Bruno CLI**
```bash
# Install Bruno CLI globally
npm install -g @usebruno/cli

# Run all tests
bru run --env Prod

# Run with detailed output
bru run --env Prod --output results.json --format json
```

**Option 2: Using npm scripts**
```bash
# Install dependencies
npm install

# Run tests
npm test

# Run with JSON output
npm run test:json

# Generate JUnit XML report
npm run test:junit

# Generate HTML report
npm run test:html
```

### Automated Testing with GitHub Actions

This repository includes a GitHub Actions workflow that automatically:
- ✅ Runs tests on every push and pull request
- ✅ Runs daily scheduled tests to catch API changes
- ✅ Can be triggered manually from the Actions tab
- ✅ Generates test reports and artifacts

**View test results:**
1. Go to the "Actions" tab in your GitHub repository
2. Click on the latest workflow run
3. View test results and download artifacts

**Manual trigger:**
1. Go to Actions → Bruno API Tests
2. Click "Run workflow"
3. Select branch and run

### Test Coverage

Tests validate:
- HTTP status codes
- Response structure and required fields
- Data types and formats
- Array lengths and sorting
- GitHub-specific validations (usernames, repo names, etc.)
- Response times
