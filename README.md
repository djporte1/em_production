# KSU Email Modules

Template-driven HTML email module system for Kent State University newsletters.

## Overview

This repository contains reusable HTML email templates for building Slate-compatible newsletters. Each template is a modular building block that can be combined to create complete emails.

## Getting Started

### Option 1: Download Starter Kit (Recommended)

Download `KSU_Email_Work_Starter.zip` from this repo. It includes:
- `CLAUDE.md` - Complete build instructions for Claude Code
- `config/colleges.json` - College-specific configurations
- `config/test_lists.json` - Internal test routing lists
- Empty `projects/` and `ARCHIVE/` folders

### Option 2: Clone This Repo

```bash
git clone https://github.com/djporte1/em_production.git
```

### Option 3: Fetch Templates Directly (for Claude Code)

Access raw template files via URL:
```
https://raw.githubusercontent.com/djporte1/em_production/main/modules/01_FEATURED_STORY.txt
https://raw.githubusercontent.com/djporte1/em_production/main/modules/05_STORY_BLOCK.txt
https://raw.githubusercontent.com/djporte1/em_production/main/docs/QA_CHECKLIST.md
```

**Base URL pattern:**
```
https://raw.githubusercontent.com/djporte1/em_production/main/{path}
```

## Module Reference

| Module | Purpose | Headline |
|--------|---------|----------|
| `00_WRAPPER_HEADER.txt` | Email structure + Kent State header | — |
| `01_FEATURED_STORY.txt` | Full-width hero image + CTA | 34px bold |
| `02_SECTION_DIVIDER.txt` | Grey section header bar | 20px bold |
| `03_STORY_TILES.txt` | 2-column alternating layout | 24px bold |
| `04_2X2_STORIES.txt` | 4-story grid | 24px bold |
| `05_STORY_BLOCK.txt` | Image left (240px), text right | 24px bold |
| `06_FEATURED_EVENTS.txt` | Calendar-style event listings | — |
| `07_HERO_STORY.txt` | Centered content on grey background | 24px bold |
| `08_SPACER.txt` | 22px vertical spacing | — |
| `09_FOOTER.txt` | Social icons + contact info | — |
| `10_DIA_EVENT_INVITE.html` | Athletics-specific template | — |
| `11_GOLD_DIVIDER.txt` | Gold bar divider | — |

## How to Use

### 1. Analyze Your Wireframe

Identify which modules you need by mapping wireframe content to module types.

### 2. Copy Template Content

Each `.txt` file contains complete HTML with placeholders:

```html
{{PROJECT_ID}}      → e.g., 26ALR148
{{HEADLINE}}        → Exact headline from wireframe
{{BODY_TEXT}}       → Body copy from wireframe
{{CTA_URL}}         → Button destination URL
{{CTA_TEXT}}        → Button text
{{IMAGE_DESCRIPTOR}} → Image suffix (e.g., GT, Dean)
```

### 3. Replace Placeholders

Extract content from your wireframe and replace placeholders. Do not edit or improve copy.

### 4. Assemble in Order

```
00_WRAPPER_HEADER
  ↓
01_FEATURED_STORY (or other content module)
  ↓
08_SPACER
  ↓
02_SECTION_DIVIDER
  ↓
... more modules ...
  ↓
09_FOOTER
```

### 5. Validate

Use `docs/QA_CHECKLIST.md` to verify your build.

## Documentation

| Document | Purpose |
|----------|---------|
| `docs/WORKFLOW.md` | Step-by-step build process |
| `docs/TEMPLATES.md` | Detailed module specs + JSON schemas |
| `docs/BRAND_STANDARDS.md` | Colors, fonts, button styles |
| `docs/QA_CHECKLIST.md` | Validation checklist |

## Examples

Complete email examples in `/examples/`:

- `Newsletter_example.html` - Standard newsletter
- `Event_invite_email.html` - Event invitation format
- `Fake_forward_example.html` - Personal forward-style email

## Brand Standards

| Element | Value |
|---------|-------|
| Kent Blue | `#003976` |
| Gold | `#EFAB00` |
| Mid-Blue (OGE) | `#4994CB` |
| Grey Background | `#EAE9E5` |
| Body Text | `#101010` |
| Font | Open Sans, Arial fallback |

## Key Rules

1. **Extract, don't improvise** - All content comes from wireframes
2. **MSO conditionals required** - Every button needs VML for Outlook
3. **Image dividers only** - Never code dividers with `bgcolor`
4. **Spacers between modules** - Add `08_SPACER.txt` between content blocks

## Image Naming Convention

```
{{PROJECT_ID}}_PX_{{MODULE}}_{{DESCRIPTOR}}.jpg

Examples:
26ALR148_PX_FEATURE_GT.png
26DIA195_PX_STORYBLOCK_Kinicki.jpg
26CEH018_PX_STORYTILE_Dean.jpg
```

## Project ID Format

`26XXX000`
- `26` = Fiscal year (FY26)
- `XXX` = College code (ALR, CEH, DIA, OGE, etc.)
- `000` = Sequential number

---

*Maintained by Kent State Division of Philanthropy and Alumni Engagement*
