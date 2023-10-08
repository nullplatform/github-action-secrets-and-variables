<h2 align="center">
    <a href="https://nullplatform.com" target="blank_">
        <img height="100" alt="nullplatform" src="https://nullplatform.com/favicon/android-chrome-192x192.png" />
    </a>
    <br>
    <br>
    Nullplatform Secrets And Variables GitHub Action
    <br>
</h2>

## Overview

The "Nullplatform Secrets And Variables" GitHub Action allows you to fetch secrets and variables for a nullplatform application. It simplifies the process of retrieving and using these secrets and variables within your GitHub Actions workflows.

## Table of Contents

- [Inputs](#inputs)
- [Outputs](#outputs)
- [Usage](#usage)
- [License](#license)

## Inputs

### `application-id`

- **Description**: The application ID to query secrets and variables.
- **Required**: Yes

### `name`

- **Description**: The parameter name to query. (Optional)
- **Required**: No

### `api-key`

- **Description**: The API key required for authentication if not already logged in. (Optional)
- **Required**: No

## Outputs

This GitHub Action dynamically generates outputs based on the retrieved build parameters. Each build parameter will be available as an output and as a environment variable.

## Usage

Here's a common use case for this GitHub Action:

```yaml
name: Fetch Nullplatform Secrets and Variables

on:
  push:
    branches:
      - main

jobs:
  fetch-secrets-and-variables:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v4

      - name: Fetch Nullplatform Secrets and Variables
        id: fetch-secrets
        uses: nullplatform/nullplatform-secrets-and-variables-action@v1
        with:
          application-id: your-app-id
          api-key: ${{ secrets.NULLPLATFORM_API_KEY }}

      - name: Display Secrets and Variables
        run: |
          echo "Retrieved Secrets and Variables:"
          echo "Variable Name: your-variable-name"
          echo "Variable Value: ${{ steps.fetch-secrets.outputs.your-variable-name }}"
```

In this example, the GitHub Action fetches secrets and variables for a Nullplatform application. You can customize it according to your workflow's requirements by specifying the `application-id`, name of the variable you want to query (or not specify to fetch all variables), and providing the `api-key` for authentication if needed.

## License

This GitHub Action is licensed under the [MIT License](LICENSE).
