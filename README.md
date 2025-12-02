# .github

![GitHub branch status](https://img.shields.io/github/checks-status/mosher-labs/.github/main)
![GitHub Issues](https://img.shields.io/github/issues/mosher-labs/.github)
![GitHub last commit](https://img.shields.io/github/last-commit/mosher-labs/.github)
![GitHub repo size](https://img.shields.io/github/repo-size/mosher-labs/.github)
![Libraries.io dependency status for GitHub repo](https://img.shields.io/librariesio/github/mosher-labs/.github)
![GitHub License](https://img.shields.io/github/license/mosher-labs/.github)
![GitHub Sponsors](https://img.shields.io/github/sponsors/mosher-labs)

⚡⚔️🌩️ Welcome to Mosher Labs! Combining Scandinavian heritage and cutting-edge cloud
technologies, we deliver precision-crafted solutions with Amazon Web Services (AWS)
and Infrastructure as Code (IaC). ⚡⚔️🌩️

## 🔐 HEIMDALLR_TOKEN Setup

The workflows use a GitHub Personal Access Token (PAT) for the `mosherlabs-heimdallr`
service account to post PR comments with proper attribution.

### Creating/Rotating the Token

1. **Login to GitHub** as `mosherlabs-heimdallr` (credentials in 1Password)
1. Go to **Settings** → **Developer settings** → **Personal access tokens** →
   **Tokens (classic)**
1. Click **Generate new token (classic)**
1. **Token settings:**
   - Note: `HEIMDALLR_TOKEN for Mosher-Labs`
   - Expiration: 90 days (recommended)
   - Scopes: `repo` (Full control of private repositories)
1. **Generate token** and copy it immediately
1. **Add to Mosher-Labs org:**

   ```bash
   echo "<token>" | gh secret set HEIMDALLR_TOKEN \
     --org Mosher-Labs --visibility all
   ```

1. **Store in 1Password** under mosherlabs-heimdallr account for future reference

### Why This Token

- Provides proper attribution (gravatar, username) on PR comments
- Shared across all Mosher-Labs repos via organization secret
- Must be rotated every 90 days for security

## 🔰 Contributing

Upon first clone, install the pre-commit hooks.

```bash
pre-commit install
```

To run pre-commit hooks locally, without a git commit.

```bash
pre-commit run -a --all-files
```

To update pre-commit hooks, this ideally should be ran before a pull request is merged.

```bash
pre-commit autoupdate
```
