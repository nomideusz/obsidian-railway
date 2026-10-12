# Deploy and Host Obsidian on Railway

[![Deploy on Railway](https://railway.com/button.svg)](https://railway.com/new/template/obsidian?referralCode=sLjDXb&utm_medium=integration&utm_source=button&utm_campaign=obsidian)

This template runs the full desktop [Obsidian](https://obsidian.md/) application in the cloud, streamed to any device through the [linuxserver.io](https://docs.linuxserver.io/images/docker-obsidian/) Selkies web interface. Open your Railway domain, log in, and Obsidian is running on the server with its files, settings and plugins persisted between visits.

## About Hosting Obsidian

Obsidian is the local-first Markdown knowledge base with graph view, plugins and canvas. The service streams a GPU-less desktop session over WebSockets with the linuxserver.io Selkies stack. Access is gated by HTTP basic auth (`CUSTOM_USER` / generated `PASSWORD`), and the application data persists on a volume at `/config`.

## Common Use Cases

- An always-on vault you can open from any device without paying for sync
- Run community plugins and automations on a vault that never sleeps
- Keep a shared team vault behind one login
- Disposable, isolated environment for opening files you do not fully trust

## Dependencies for Obsidian Hosting

- None. Single service, no database.

### Deployment Dependencies

- [linuxserver.io Obsidian image docs](https://docs.linuxserver.io/images/docker-obsidian/)
- [Selkies project](https://github.com/selkies-project)

### Implementation Details

**First use:** open your Railway domain, log in with `CUSTOM_USER` and the generated `PASSWORD` (service Variables tab), and the Obsidian window appears. On touch devices, use the sidebar for keyboard and gestures. Files you save under `/config` (the home directory) persist; use the built-in file manager or drag and drop into the browser window to upload, and the download tray to fetch files back.

Notes and limits:

- Keep the login strong: the password gate is the whole security model.
- Rendering is CPU-based (no GPU on Railway). Fine for the application UI and light media; not for GPU-accelerated work.
- Give the service 2 GB of RAM or more; desktop applications are memory-hungry.
- Only `/config` persists. Anything installed outside it is gone after a redeploy.
- Want a whole desktop instead of one app? The same author publishes a [Linux Desktop](https://railway.com/deploy/linux-desktop?referralCode=sLjDXb) template.

## Why Deploy Obsidian on Railway?

Railway is a singular platform to deploy your infrastructure stack. Railway will host your infrastructure so you don't have to deal with configuration, while allowing you to vertically and horizontally scale it.

By deploying Obsidian on Railway, you are one step closer to supporting a complete full-stack application with minimal burden. Host your servers, databases, AI agents, and more on Railway.
