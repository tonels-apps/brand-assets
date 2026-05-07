# Brand Assets

Official branding assets for TONELS.

## Contents

```
icons/          # Icon PNG assets (dark & light variants)
logo/
  badge/        # Badge & logotype variants
  icons/        # Icon-only logo variants (no background, dark, light)
colors/         # Color palette (JSON + Markdown)
guildlines/     # Brand usage guidelines
```

## Usage

Do not alter logo proportions or colors.

## CDN / Asset URLs

All assets are published to Cloudflare R2 on every push to `main`. The public base URL follows the pattern:

```
https://<your-r2-public-domain>/<asset-path>
```

Examples:
```
/icons/tonl-dark.png
/icons/tonl-light.png
/logo/badge/badge-tonels.png
/logo/badge/tonl-logo-text-dark.png
/logo/badge/tonl-logo-text-light.png
/logo/icons/tonels-dark.png
/logo/icons/tonels-light.png
/logo/icons/tonl-nobg.png
/colors/color.json
/colors/palette.md
/guidelines/brand-guideline.md
```

## CI/CD

GitHub Actions workflow: [`.github/workflows/deploy-assets.yml`](.github/workflows/deploy-assets.yml)

Required **GitHub repository secrets**:

| Secret | Description |
|--------|-------------|
| `CLOUDFLARE_ACCOUNT_ID` | Cloudflare account ID (found in the dashboard URL or *Account Home*) |
| `R2_ACCESS_KEY_ID` | R2 API token — Access Key ID (generated from *R2 → Manage R2 API Tokens*) |
| `R2_SECRET_ACCESS_KEY` | R2 API token — Secret Access Key |
| `R2_BUCKET_NAME` | Name of the target R2 bucket (e.g. `tonl-brand-assets`) |

### How to add secrets

1. Go to your GitHub repo → **Settings → Secrets and variables → Actions**
2. Click **New repository secret** for each row in the table above

### How to create an R2 API token

1. Cloudflare Dashboard → **R2** → **Manage R2 API Tokens**
2. Click **Create API token**
3. Set permissions to **Object Read & Write** scoped to your bucket
4. Copy the **Access Key ID** and **Secret Access Key** — save them immediately, the secret is only shown once
