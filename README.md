# OpenMeow

> The notch becomes a workstation.
> A native macOS AI shell that lives where your cursor already does.

**OpenMeow** puts ambient AI in the one place every pro looks at all day — the notch of your MacBook Pro. Hit `⌃⌘` from anywhere and a native shell drops out of the notch: ask a question and the answer streams inline, or hand a task to a browser agent and watch it drive real Chromium against the live web. No tab switch. No sidebar. No Electron.

This repo is the **public download channel** for OpenMeow binaries. Source code lives in a separate private repository.

---

## Download

**Latest release (direct DMG):**

<https://github.com/OpenSorceryAI/open-meow-downloads/releases/latest/download/OpenMeow.dmg>

Every release ships a signed and notarized `.dmg` — Gatekeeper-accepted on first launch, no right-click-Open workaround needed.

- **Signed with** Developer ID Application (Soul Protocol LLC)
- **Notarized** by Apple and stapled
- **Evergreen permalink** — the URL above always resolves to the most recent release's `OpenMeow.dmg` asset

Browse all past versions → [Releases](https://github.com/OpenCoven/open-meow-downloads/releases)

---

## System requirements

- **macOS 14.0 (Sonoma) or later**
- **Apple Silicon or Intel** — universal build
- **MacBook Pro with a notch** — OpenMeow is designed for the 14"/16" notched hardware. It will run on non-notched Macs but the ambient state sits under the menu bar as a floating pill instead of tracing the notch silhouette.

---

## Install

1. **Download** the DMG from the link above.
2. **Open** it and drag **OpenMeow** into `/Applications`.
3. **Launch** from Applications. Grant permission prompts on first run:
   - **Accessibility** — required for the `⌃⌘` global shortcut to work system-wide.
   - **Automation** — for browser agent tasks.
4. **Configure the gateway** — open **Settings → Gateway** and paste your OpenClaw gateway URL + token. Without a gateway configured, OpenMeow has no model access and agent runs will fail.

---

## What's in the app

### Three states, one surface

| State | Trigger | Size | Purpose |
|-------|---------|------|---------|
| **Resting** | Default | 180×32pt — traces the notch cutout exactly | Invisible until you need it |
| **Expanded** | `⌃⌘` | Grows vertically up to 7 lines | Quick prompts, agent chips |
| **Workstation** | `return` from expanded | 680×440pt panel | Full conversation surface, thread history |

Press `esc` to dismiss from any state.

### Subagents

OpenMeow isn't one agent — it's a routing surface for specialized subagents, each with their own tools and personality:

- **Kitty** — the general-purpose chat agent. Defaults to Haiku 4.5 for snappy back-and-forth. Purple accent.
- **Fishy** — the browser agent. Drives a real Chromium via the TinyFish substrate to reach the 90% of the web that lives behind logins and UIs rather than APIs. Orange accent. Returns structured result cards with source links and live preview URLs.
- **Cody** — coding agent (roadmap — coming soon).

Pick an agent from the chip row in the expanded shell, or type to the default (Kitty).

### Why native

- **First paint under 200ms** from `⌃⌘` — streaming tokens render as they arrive, nothing blocks the UI thread.
- **No Electron.** Pure AppKit/SwiftUI with native NSTextView composers, native streaming, native typography.
- **Keychain-backed credentials** — gateway tokens never hit disk in plaintext.
- **Threads persist across days.** Conversation history is local and queryable.

---

## Release notes

Each release in this repo includes full changelog notes. Browse them on the **[Releases page](https://github.com/OpenSorceryAI/open-meow-downloads/releases)**, or pull the latest directly:

```sh
gh release view --repo OpenSorceryAI/open-meow-downloads
```

The **OpenMeow-vX.Y.Z.dmg** and **OpenMeow.dmg** assets on each release are byte-identical — the generic name exists so the evergreen permalink above always resolves.

---

## Support

- **Issues / bugs:** open an issue on this repo — [New issue](https://github.com/OpenCoven/open-meow-downloads/issues/new)
- **Email:** [val@opensorcery.ai](mailto:val@opencoven.ai)
- **Homepage:** <https://openmeow.ai> *(landing page)*

---

## About OpenSorceryAI

OpenMeow is an **OpenSorceryAI** product — the consumer surface for ambient AI on macOS.

The product architecture in one sentence: **OpenMeow owns the native surface; TinyFish owns the browser substrate; OpenClaw routes between them.**

- **Company:** [OpenSorceryAI](https://github.com/OpenCoven)
- **Landing:** <https://openmeow.ai>

---

## Legal

© 2026 Soul Protocol LLC. All rights reserved.

OpenMeow binaries are distributed under the terms included inside each DMG. The binaries are **proprietary**; the source code is not open-sourced. This repository contains only downloadable build artifacts and this README.

---

*Last updated: 2026-04-21*
