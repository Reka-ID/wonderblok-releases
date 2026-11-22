# Wonderblok

**A design canvas your AI coding agent works on with you, over MCP.**

Claude Code, Codex, Claude Desktop or any MCP client can read your design, follow your design system and edit the same file you have open. Your files stay on your device.

[Website](https://www.wonderblok.app) · [Docs](https://www.wonderblok.app/docs) · [Universe patterns](https://www.wonderblok.app/universe) · [Download](https://github.com/Reka-ID/wonderblok-releases/releases/latest)

![Claude Code drafts an onboarding flow from Universe in Wonderblok, on your tokens, and builds it](https://www.wonderblok.app/readme/demo.gif?v=2)

## What it does

- **A real canvas.** Frames with auto layout, components, tokens with modes (light and dark), vector paths, prototypes, and export to PNG, JPG, WebP, SVG and PDF.
- **Your agent edits, not just reads.** It reads frames, components and tokens, and applies edits to the file you have open. You and the agent can work on the same file at once.
- **Rules before edits.** Every edit from an agent must carry the hash of your current design rules, so it has to read them first. Paint and fonts must use your tokens: an off-system color is rejected.
- **Start from proven patterns.** [Universe](https://www.wonderblok.app/universe) is a library of app UI patterns and user flows (onboarding, log in, send money, checkout, empty states and more). Your agent reads a flow and draws it on your design system.
- **Local files.** Designs are `.wonderblok` files on your device.

Runs on macOS, Windows and Linux.

## Connect your agent

Install the app from [Releases](https://github.com/Reka-ID/wonderblok-releases/releases/latest), then add the MCP server once per device. Settings › Agents (MCP) in the app shows the exact command for your install.

**Claude Code** (macOS path):

```bash
claude mcp add --scope user wonderblok -- \
  "/Applications/Wonderblok.app/Contents/MacOS/wonderblok-app" mcp
```

**Codex** (`~/.codex/config.toml`):

```toml
[mcp_servers.wonderblok]
command = "/Applications/Wonderblok.app/Contents/MacOS/wonderblok-app"
args = ["mcp"]
```

Then try: *"List my open Wonderblok files and describe the first frame."*

## MCP tools

| Tool | What it does |
| --- | --- |
| `list_files` | The `.wonderblok` files open in the app |
| `get_guidelines` | Your design rules and their hash (every edit passes it) |
| `get_tree`, `get_node` | Outline of a board or a layer, and one layer's properties |
| `get_tokens` | The file's design tokens |
| `apply_ops` | Insert, update, move and delete layers, set tokens |
| `write_page` | Import a page written in HTML and CSS as frames, mapped to your tokens |
| `use_pattern` | Read a Universe flow: its screens, rules and states |
| `get_notes`, `ack_note` | Notes people left for the agent on layers |
| `screenshot` | A PNG of a layer as the app renders it |

Full reference: [wonderblok.app/docs](https://www.wonderblok.app/docs).

## Pricing

Every plan, Free included, has the full canvas and MCP access. Free has an allowance of MCP calls and Pro raises it; Universe is part of Pro. See [pricing](https://www.wonderblok.app/pricing).

## About this repository

This repository holds the installers and update files for the desktop app. Report issues at [wonderblok.app](https://www.wonderblok.app) or open an issue here.
