# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based GitHub Pages site for [t0p1]The Elite alliance in the game "Last Z: Shooter Run". It provides strategy guides, daily tips, and weekly Canyon Clash battle plans.

**Live Site:** https://karmapolicet2.github.io/TheElite/

## Architecture

### Content Organization

Posts are organized into three categories via the `categories` front matter field:
- `canyon-clash` - Weekly PvP strategy posts
- `daily-tips` - Day-specific optimization guides
- `events` - Event and mini-game strategy guides

Each category page (`canyon-clash.md`, `daily-tips.md`, `events.md`) dynamically displays posts from its category using Liquid templates.

### Key Configuration

**_config.yml critical settings:**
- `baseurl: "/TheElite"` - Required for GitHub Pages subdirectory deployment; all asset paths depend on this
- `future: true` - Allows publishing posts with future dates (essential for pre-publishing event strategies)
- `permalink: /:categories/:year/:month/:day/:title:output_ext` - Creates category-based URL structure

### Liquid Template Pattern

All category pages use this pattern to handle empty/null categories gracefully:

```liquid
{% assign posts = site.categories.CATEGORY | default: empty | sort: 'date' | reverse %}
```

The `| default: empty` filter prevents "Cannot sort a null object" errors when no posts exist in a category.

## Post Creation Guidelines

### File Naming Convention

**CRITICAL:** Use short filenames for easy URL sharing. The filename after the date becomes part of the URL.

Examples:
- Canyon Clash: `2026-02-06-CC.md` → `/canyon-clash/2026/02/06/CC/`
- Daily Tips: `2026-02-03-monday.md` → `/daily-tips/2026/02/03/monday/`
- Events: `2026-02-01-zombie-horde.md` → `/events/2026/02/01/zombie-horde/`

**Pattern:** `YYYY-MM-DD-short-slug.md` where `short-slug` is as brief as possible.

### Front Matter Templates

**Canyon Clash Post:**
```yaml
---
layout: post
title: "Canyon Clash: February 6 Battle Plan"
date: 2026-02-06
categories: canyon-clash
tags: [canyon-clash, pvp, strategy, coordination]
---
```

**Daily Tips Post:**
```yaml
---
layout: post
title: "Monday Tips: Resource Farming"
date: 2026-02-03
categories: daily-tips
tags: [monday, resources, farming]
---
```

**Event Guide Post:**
```yaml
---
layout: post
title: "Event Guide: Zombie Horde"
date: 2026-02-01
categories: events
tags: [event-name, strategy]
---
```

### Time Convention

**Always use "Apocalypse Time" for all event times.** Apocalypse Time = PST + 6 hours.

Example: 12:00 PM PST = 18:00 (6:00 PM) Apocalypse Time

## Deployment

Changes pushed to `main` branch automatically deploy via GitHub Pages Actions workflow.

**Local testing:**
```bash
bundle install
bundle exec jekyll serve
# Visit http://localhost:4000/TheElite
```

Note the `/TheElite` path matches the baseurl configuration.

## Layout Usage

- `layout: home` - Home page (index.md), automatically lists recent posts
- `layout: page` - Static pages (about.md, canyon-clash.md, daily-tips.md, events.md)
- `layout: post` - All blog posts in _posts/

The Minima theme provides these layouts. Other themes may not support multiple layouts.
