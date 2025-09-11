# Sync Flows to lamatic

[![GitHub Marketplace](https://img.shields.io/badge/Marketplace-Sync%20Flows%20to%20lamatic-red?logo=github)](https://github.com/marketplace/actions/sync-flows-to-lamatic)

## 📌 Features

- Detects changed flow files in the `lamatic/flows/` directory on each run.
- Updates changed flow files via GraphQL API to the Lamatic platform.
- Optionally deploys updated flows automatically based on input flag.
- Outputs the list of updated flow slugs for downstream use.

## 🚀 Usage

### Prerequisites

- A GitHub repository containing flow files inside the `lamatic/flows/` directory.
- Lamatic API credentials with permissions to update and deploy flows:
  - `LAMATIC_PROJECT_ENDPOINT`
  - `LAMATIC_PROJECT_API_KEY`
  - `LAMATIC_PROJECT_ID`
  - `LAMATIC_AUTO_DEPLOY_PROJECT` (optional flag to trigger auto deployment)

### Workflow Example

```yaml
  - name: Sync Flows to lamatic
    uses: Lamatic/sync-flows-to-lamatic@v1.0
    with:
      lamatic-endpoint: ${{ secrets.LAMATIC_PROJECT_ENDPOINT }}
      api-key: ${{ secrets.LAMATIC_PROJECT_API_KEY }}
      project-id: ${{ secrets.LAMATIC_PROJECT_ID }}
      auto-deploy: ${{ secrets.LAMATIC_AUTO_DEPLOY_PROJECT }}

```

### Inputs

| Input              | Description                               | Required | Default                          |
|--------------------|-------------------------------------------|---------|---------------------------------|
| `lamatic-endpoint` | Lamatic API endpoint URL                  | Yes     | `${{ secrets.LAMATIC_PROJECT_ENDPOINT }}` |
| `api-key`          | Authorization API key for Lamatic API    | Yes     | `${{ secrets.LAMATIC_PROJECT_API_KEY }}`  |
| `project-id`       | Lamatic project identifier                | Yes     | `${{ secrets.LAMATIC_PROJECT_ID }}`       |
| `auto-deploy`      | Flag to control automatic deployment     | Yes     | `${{ secrets.LAMATIC_AUTO_DEPLOY_PROJECT }}` (true/false) |

---

### Versioning

To use a specific version, reference it in your workflow like so:

```yaml
- uses: Lamatic/sync-flows-to-lamatic@v1.0
```
