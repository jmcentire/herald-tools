# herald-tools

Marketing landing page and docs for [Herald](https://github.com/jmcentire/herald) — the lightweight webhook relay and message queue for AI agents and local services that can't expose a public endpoint.

Static HTML, served by nginx from a small Fly.io app. Two pages:

- `index.html` → `https://herald.tools/`
- `docs/index.html` → `https://herald.tools/docs`

The Herald API (the actual webhook relay service) lives at `https://proxy.herald.tools/` and is served from a different repo (`jmcentire/herald`).

## Why this is its own repo

The marketing copy and the API/server are different concerns with different release cadences. Keeping the static landing page out of the Herald server binary makes it easier to iterate on copy, design, and SEO without redeploying the API.

## Local

Open `index.html` directly in a browser, or:

```bash
docker build -t herald-tools .
docker run -p 8080:8080 herald-tools
```

Then visit `http://localhost:8080`.

## Deploy

```bash
fly deploy
```

DNS: `herald.tools` is a Fly custom domain attached to this app.
