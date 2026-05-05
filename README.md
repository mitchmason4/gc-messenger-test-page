# GC Messenger Test Page

A lightweight, static web tool for quickly testing and sharing Genesys Cloud Messenger (AVA) deployments. No backend, no build tools — just a single HTML file hosted on GitHub Pages.

## Live Page

**https://mitchmason4.github.io/gc-messenger-test-page/**

## What It Does

Enter a Genesys Cloud **Deployment ID** and **Region**, and the page dynamically loads the Messenger chat widget. The configuration is encoded in the URL, so you can share a direct link with teammates or stakeholders — they'll see the widget immediately without any setup.

### Example Shareable URL

```
https://mitchmason4.github.io/gc-messenger-test-page/?deploymentId=YOUR-UUID-HERE&region=mypurecloud.com
```

## Features

- **No setup required** — Just open the page and enter your deployment details
- **Shareable URLs** — Configuration is stored in query parameters for easy sharing
- **All GC regions supported** — Dropdown with all 9 standard Genesys Cloud regions
- **Error handling** — Clear messages for failed loads or invalid deployments
- **Reset & switch** — Easily switch between different deployments
- **Mobile friendly** — Responsive design works on any device
- **Zero dependencies** — Single HTML file, no build step, no backend

## Supported Regions

| Region | Identifier |
|--------|-----------|
| Americas (US East) | `mypurecloud.com` |
| Americas (US West) | `usw2.pure.cloud` |
| Canada | `cac1.pure.cloud` |
| EMEA (Dublin) | `mypurecloud.ie` |
| EMEA (London) | `euw2.pure.cloud` |
| EMEA (Frankfurt) | `mypurecloud.de` |
| Asia Pacific (Sydney) | `mypurecloud.com.au` |
| Asia Pacific (Tokyo) | `mypurecloud.jp` |
| Asia Pacific (Seoul) | `apne2.pure.cloud` |

## How It Works

1. User enters a Deployment ID and selects a Region
2. The page constructs the Genesys Cloud Messenger bootstrap snippet dynamically
3. The snippet is injected into the page, loading the widget from `https://apps.{region}/genesys-bootstrap/genesys.min.js`
4. The URL is updated with query parameters so the link can be shared
5. Anyone opening the shared link gets the widget auto-loaded

## Deployment

This tool is designed to run on GitHub Pages. It's a single `index.html` file with inline CSS and JavaScript — no build step needed.

To deploy your own instance:

1. Fork or clone this repo
2. Enable GitHub Pages in repo Settings → Pages → Source: "Deploy from a branch" → `main` / `/ (root)`
3. Your page will be live at `https://<username>.github.io/gc-messenger-test-page/`

## Local Development

Just open `index.html` in a browser. That's it. No server needed.

```bash
open index.html
```

## URL Parameters

| Parameter | Required | Description |
|-----------|----------|-------------|
| `deploymentId` | Yes | The Genesys Cloud Web Messaging deployment UUID |
| `region` | Yes | The Genesys Cloud region identifier (e.g., `mypurecloud.com`) |

Both parameters must be present for the widget to auto-load. If only one is provided, the form will be pre-filled but the widget won't load until the user submits.

## License

MIT
