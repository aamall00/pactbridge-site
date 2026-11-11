# pactbridge-site

Static website for **pactbridge.in**, hosted on Azure Static Web Apps (Free tier).

| Path | Page |
|---|---|
| `site/index.html` | PactBridge home page |
| `site/insureremind/index.html` | InsureRemind landing page (Log in → `https://app.pactbridge.in/`) |
| `site/404.html` | Not-found page |
| `site/staticwebapp.config.json` | Redirects, 404 override, security headers |

Add a product page by creating `site/<product>/index.html` and linking it from `site/index.html`.

## Deploy
Every push to `main` deploys via `.github/workflows/deploy.yml`. The workflow needs the repository secret
`AZURE_STATIC_WEB_APPS_API_TOKEN` (the Static Web App's deployment token).

Azure resource: Static Web App `swa-pactbridge-site` in resource group `rg-insureremind-prod`.

## Preview locally
```
python -m http.server 8080 -d site
```
