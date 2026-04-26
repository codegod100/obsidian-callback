# Obsidian Unified OAuth Callback

A single static GitHub Pages page that redirects OAuth callbacks back to Obsidian plugins.

## How it works

Each plugin registers a redirect URI with a `scheme` query parameter:

```
https://codegod100.github.io/obsidian-callback/callback.html?scheme=semblage-oauth
```

When the OAuth provider redirects back with authorization params, this page reads `scheme`, strips it, and redirects to:

```
obsidian://semblage-oauth?code=xxx&state=yyy
```

## Supported plugins

- **Semblage** — `?scheme=semblage-oauth`
- **MyST** — `?scheme=myst-oauth`
- *(freeq-chat coming soon)*

## Deploying

Push this repo to GitHub and enable GitHub Pages on the root directory.
