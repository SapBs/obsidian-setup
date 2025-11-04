
# 🎨 My Obsidian Vault Setup Guide

> A comprehensive guide to my Obsidian setup for learning frontend technologies, English, and LeetCode problem-solving

## Overview

As I'm extending my knowledge in frontend technologies, learning English, and solving LeetCode issues, I've created this vault to systematize my thoughts and progress. This guide shares the useful plugins and approaches that have helped me stay organized and productive.

---

## 🎨 Visual Plugins

### Style Settings + Baseline Theme

I use **Baseline** theme with **Style Settings** plugin for a clean, modern look. As a graphics enthusiast, visual appeal matters a lot to me.

#### My Style Settings Configuration

```json
{
  "baseline-style@@accented-interface": true,
  "baseline-style@@color-scheme-light": "notion-light",
  "baseline-style@@color-scheme-dark": "notion-dark",
  "baseline-style@@color-scheme-accent": false,
  "baseline-style@@radius-modifier": 1.5,
  "baseline-style@@layout-style": "layout-frame",
  "baseline-style@@input-style": "input-elevated",
  "baseline-style@@status-bar-style": "status-bar-baseline",
  "baseline-style@@anim-motion-baseline": "cubic-bezier(0.1, 0, 0.1, 1.25)",
  "baseline-style@@anim-speed-modifier": 1.6,
  "baseline-style@@tabs-style": "tabs-default",
  "baseline-style@@labeled-tabs": "labeled-tabs-off",
  "baseline-style@@nav-item-active-style": "nav-item-baseline",
  "baseline-style@@colorful-folders": "colorful-folders-off",
  "baseline-style@@full-item-name": false,
  "baseline-style@@hover-ribbon": true,
  "baseline-style@@hover-sidedock": false,
  "baseline-style@@hover-sidedock-trigger-area": "8px",
  "baseline-style@@nav-indentation-guide-width": "1px",
  "baseline-style@@nav-indentation-guide-color": "var(--color-accent)",
  "baseline-style@@block-width-off": false,
  "baseline-style@@icon-stroke-modifier": 0.75,
  "baseline-style@@density-modifier": 1.25,
  "baseline-style@@metadata-style": "metadata-cupertino"
}
```

**Why I love it:**
- Clean, modern aesthetic similar to Notion
- Customizable radius and animations
- Perfect balance between beauty and functionality

### Iconize

I use **Iconize** to add icons to folders and highlight important areas. It's a small enhancement that makes navigation much more intuitive.

**Usage:**
- Right-click on folders/files → Set icon
- Choose from Lucide icons or custom icons
- Helps visual organization and quick identification

### Banners

**Banners** plugin transforms my homepage and important notes into visually appealing pages. I prefer:
- **Style**: Gradient
- **Height**: 400px
- **Source**: Pinterest/Unsplash for beautiful images

**How to use:**
```yaml
---
banner: "https://example.com/image.jpg"
banner_y: 0.5  # Vertical position (0-1)
banner_x: 0.5  # Horizontal position (0-1)
---
```

---

## 🔧 Useful Plugins

### Homepage

**Homepage** plugin opens my main dashboard (`00_HOME/Home.md`) automatically when Obsidian starts. Perfect for staying focused and organized.

**Configuration:**
- Open on startup: ✅
- Open mode: Replace all open notes
- View: Reading view

### Dataview

**Dataview** is essential for creating dynamic dashboards and tracking progress. I use it for:
- Health & Mood Dashboard (tracking pushups and mood)
- Weekly summaries
- Learning progress tracking

**Example:**
```dataview
TABLE pushups, mood
FROM "01_Daily"
WHERE pushups != null OR mood != null
SORT created DESC
```

### Heatmap Calendar

**Heatmap Calendar** creates GitHub-style activity calendars for tracking habits. I use it to visualize:
- Daily pushups progress
- Mood tracking over time
- Combined activity heatmaps

### Tracker

**Tracker** plugin provides beautiful line charts and graphs. Great for visualizing trends in:
- Habit tracking
- Mood progression
- Learning metrics

### Tasks

**Tasks** plugin helps me manage todos across the vault. I use it for:
- Daily task tracking
- Weekly goals
- Learning objectives

### Calendar

**Calendar** plugin provides a visual calendar view of daily notes. Perfect for:
- Quick navigation between daily notes
- Seeing patterns in activity
- Planning ahead

### Journals

**Journals** plugin (similar to Daily Notes but with more features) helps organize:
- Daily reflections
- Weekly reviews
- Monthly planning

### Home Tab

**Home Tab** provides an alternative homepage experience with tabs and quick access.

---

## 📁 My Vault Structure

```
DreamRoadmap/
├── 00_HOME/
│   └── Home.md                    # Main dashboard with banners
├── 01_Daily/
│   ├── Daily Index.md
│   └── YYYY-MM-DD.md             # Daily notes with pushups/mood
├── 03_Areas/
│   ├── Career Migration/
│   │   └── Migration Plan.md
│   ├── Health/
│   │   └── Habit Tracker.md
│   └── Learning/
│       ├── English.md
│       ├── LeetCode.md
│       ├── Nuxt.md
│       └── Three.js.md
├── 04_Projects/
│   └── Move to Europe/
│       └── Project Tracker.md
├── 05_Resources/
│   └── Programming Thoughts/
│       └── README.md
├── 07_Templates/
│   ├── Daily Note.md
│   └── Learning Note.md
└── 08_Dashboards/
    └── Health & Mood Dashboard.md
```

### Why This Structure?

1. **00_HOME/** - Starting point, always visible
2. **01_Daily/** - Daily tracking and journaling
3. **03_Areas/** - Life areas (P.A.R.A. method inspired)
4. **04_Projects/** - Active projects with timelines
5. **05_Resources/** - Reference materials
6. **07_Templates/** - Reusable note templates
7. **08_Dashboards/** - Data visualization and analytics

---

## 🎯 Workflow Examples

### Daily Workflow

1. Open Obsidian → Homepage loads automatically
2. Click "Create Daily Note" → Template opens
3. Fill in:
   - Today's intent
   - Tasks
   - Pushups count
   - Mood (0-10)
4. Review dashboard at end of day

### Learning Workflow

1. Create Learning Note from template
2. Take notes while studying
3. Link to related daily notes
4. Track progress in Learning area folder

### LeetCode Practice

1. Create session note (linked from LeetCode.md)
2. Document problem approach
3. Note solution patterns
4. Review weekly in dashboard

---

## 💡 Tips & Tricks

### 1. Use Callouts for Structure
```markdown
> [!tip] Pro Tip
> Use callouts to organize information visually
```

### 2. Link Everything
- Link related notes
- Use [[wikilinks]] for easy navigation
- Create MOCs (Maps of Content) for topics

### 3. Use Templates
- Daily Note template ensures consistency
- Learning Note template for structured study
- Templates save time and maintain format

### 4. Dashboard Everything
- Create dashboards for important metrics
- Use Dataview for dynamic content
- Visualize progress with charts

### 5. Banners for Important Pages
- Add banners to homepage
- Use banners for project pages
- Makes navigation more enjoyable

---

## 🔄 Continuous Improvement

I'm constantly refining my setup:

- **Experimenting with**: New visualization plugins
- **Learning**: Better Dataview queries
- **Improving**: Dashboard designs
- **Exploring**: Better organization methods

---

## 📚 Resources

- [Obsidian Forum](https://forum.obsidian.md/)
- [Obsidian Discord](https://discord.gg/obsidianmd)
- [Plugin Documentation](https://obsidian.md/plugins)
- [Dataview Documentation](https://blacksmithgu.github.io/obsidian-dataview/)

---

## 🎨 Custom CSS Snippet

Here's a simple CSS snippet I use for additional visual enhancements:

```css
/* Custom styling for better readability */
.markdown-preview-view {
  max-width: 900px;
  margin: 0 auto;
}

/* Beautiful callouts */
.callout {
  border-radius: 8px;
  padding: 1em;
}

/* Smooth transitions */
* {
  transition: all 0.2s ease;
}
```
