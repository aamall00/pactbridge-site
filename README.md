# pactbridge-site

Static website for **pactbridge.in**, hosted on Azure Static Web Apps (Free tier).

| Path | Page |
|---|---|
| `site/index.html` | PactBridge landing page (self-contained; its `#insureremind` section links to `https://app.pactbridge.in/`) |
| `site/styles.css` | Styles for the 404 page |
| `site/404.html` | Not-found page |
| `site/insureremind/index.html` | Forwards `/insureremind` to `/#insureremind` (meta refresh + JS) |
| `site/staticwebapp.config.json` | `/login` redirect, 404 override, security headers |

Add a product page by creating `site/<product>/index.html` and linking it from `site/index.html`.

## Deploy
Every push to `main` deploys via `.github/workflows/deploy.yml`. The workflow needs the repository secret
`AZURE_STATIC_WEB_APPS_API_TOKEN` (the Static Web App's deployment token).

Azure resource: Static Web App `swa-pactbridge-site` in resource group `rg-insureremind-prod`.

## Preview locally
```
python -m http.server 8080 -d site
```
