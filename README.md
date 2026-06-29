# Croco — Project Manager

A fast, minimal desktop project manager built for developers. ~8 MB binary, no browser engine overhead.

![Platform](https://img.shields.io/badge/platform-Windows-blue)
![Version](https://img.shields.io/github/v/release/ImSkuller/croco-releases?label=latest)
![Downloads](https://img.shields.io/github/downloads/ImSkuller/croco-releases/total?label=downloads)
![License](https://img.shields.io/badge/license-Proprietary-red)
<a href="https://www.producthunt.com/products/croco-2?embed=true&amp;utm_source=badge-featured&amp;utm_medium=badge&amp;utm_campaign=badge-croco-2" target="_blank" rel="noopener noreferrer"><img alt="Croco - The project manager built for developers, not managers. | Product Hunt" width="250" height="54" src="https://api.producthunt.com/widgets/embed-image/v1/featured.svg?post_id=1183840&amp;theme=dark&amp;t=1782743710597"></a>

## Download

Go to the [**Releases**](https://github.com/ImSkuller/croco-releases/releases) tab and download the installer for your platform.

| Platform | File |
|---|---|
| Windows | `Croco_x.x.x_x64_setup.exe` |

Run the installer — Croco installs to `C:\Program Files\Croco` and adds a Start Menu shortcut.

## Features

- **Projects** — Create from 35 starter templates including Minecraft (Fabric, Paper, Forge, Spigot) and Discord (discord.py, discord.js) presets; redesigned minimal two-column create flow; import existing folders; open in IDE with one click; tag and filter
- **Git & GitHub** — Commit, push, pull, view log, create branches; auto-create GitHub repos (choose public or private) on project creation
- **Todos** — Scoped to projects or global, with priorities, due dates, completion date tracking, and a 6-day revert lock
- **Notes** — Markdown editor with live preview, paste images from clipboard, archive/unarchive, star, pin, and link to projects
- **Activity Log** — Tracks all project, todo, note, git, run, and settings events; filterable by category, grouped by day
- **AI Assistant** — Claude Code, Codex, Aider, Gemini CLI, Ollama; per-project streaming chat with compressed context
- **Terminal** — Per-project run commands with progress-bar support, graceful stop, and shell preference
- **Ideas Scratchpad** — 69 curated ideas across 11 categories; canvas drawing with undo and eraser tool
- **20 Themes** — Default Dark, Acidic Croco, Glassy Croco (iOS liquid glass), Croco Lite, Croco Sparrow, Monkey D. Croco (One Piece), Catppuccin, Tokyo Night, Dracula, Nord, Gruvbox, One Dark, GitHub Dark/Light, NeoVim, Vim
- **SQLite Storage** — Switch from JSON files to a bundled SQLite database via Settings → Storage; one-click migration, JSON files kept as backup
- **Croco Run** — Retro dino-style easter egg game; type `croco:game` in the search bar or click your profile 5 times; high score saved locally
- **Keyboard Shortcuts** — Chord navigation (G+key), remappable via Settings → Shortcuts; press `?` to see them all
- **Auto-updates** — In-app update check; installs silently and restarts automatically

## System Requirements

- Windows 10 or later (x64)
- ~30 MB disk space
- Internet connection for GitHub features and update checks (optional)

## Updates

Croco checks for updates on launch. When one is available you'll see a banner in the sidebar. Click **Settings → Updates → Install** — the update downloads and installs silently. The app restarts automatically.

## Development

**Requirements:** [Rust](https://rustup.rs) + Node.js 18+

```bash
npm install
npm run tauri:dev     # launch Vite dev server + Tauri window
npm run tauri:build   # production build
```

The installer is written to `src-tauri/target/release/bundle/`.

## Releasing

Push a version tag to trigger the cross-platform GitHub Actions build:

```bash
git tag v1.x.x-beta
git push origin v1.x.x-beta
```

## Tech Stack

| Layer | Technology |
|---|---|
| UI | React 19, React Router v7, Vite 8 |
| Desktop | Tauri 2 (Rust) |
| Styling | CSS custom properties (20-theme system) |
| Fonts | Geist, Inter, IBM Plex Sans, Nunito, DM Sans, Geist Mono |
| Storage | JSON files or bundled SQLite (`rusqlite` with `bundled` feature) |
| HTTP | reqwest (GitHub API, community tags) |

## Version History

| Version | Highlights |
|---|---|
| `1.2.12` | Minecraft Developer Patch: Fabric, Paper, Forge, Spigot + discord.py + discord.js templates; redesigned two-column project create; Glassy Croco theme (iOS liquid glass, floating sidebar); Monkey D. Croco rework (One Piece palette); removed Bloody Croco + Pasta Attack; SQLite storage backend with one-click JSON→SQLite migration (Settings → Storage); Croco Run easter egg game (`croco:game` or 5× profile click) |
| `1.2.11` | Keyboard Warrior Patch: Settings → Shortcuts section with click-to-capture remapping for all global shortcuts; `Ctrl+,` → Settings; G+I/A/F/Q nav shortcuts; responsive shortcuts modal; Pasta Attack theme; straw hat easter egg fixed on Monkey D. Croco; word count footer shows unarchived notes only |
| `1.2.10` | 4 new themes (Bloody Croco, Croco Lite, Croco Sparrow, Monkey D. Croco + straw hat easter egg); improved sidebar nav visibility; archive button always visible on notes; sidebar badge shows only unarchived notes; todo rows show linked project name; long todos expand inline; auto-relaunch after update installs; stale-while-revalidate data cache for faster navigation |
| `1.2.9` | GitHub OAuth App client ID; version bump for OAuth login fix |
| `1.2.8` | Activity filter bar redesigned; update banner in sidebar; note pinning in project detail; silent NSIS install (no popup, auto-restart); Ideas: undo, eraser tool, 12 new SaaS revenue ideas; GitHub OAuth-only login; bug fixes |
| `1.2.7` | Todo completion dates; 6-day revert lock; note image paste; note archive/unarchive; independent GitHub repo visibility on project creation |
| `1.2.6` | Croc app icon; activity log improvements; publisher branding; New Project button made primary; Open IDE button on project detail |
| `1.2.5` | Fix update notification spam; GitHub PAT validation; optional OAuth Device Flow login; fix dark theme contrast; DM Sans font |
| `1.2.3` | App renamed to Croco; crocodile logo; activity log extended; completed todos grouped by date |
| `1.2.0` | Shell preference; progress-bar terminal; 57 ideas + Scribble Pad; note-todo linking; AI API keys; update notifications |
| `1.1.x-beta` | AI assistant; theming overhaul; 29 templates; live sidebar counts; Tauri v2 rebuild |

## Support

Found a bug or have a suggestion? Open an [issue](https://github.com/ImSkuller/croco-releases/issues).
