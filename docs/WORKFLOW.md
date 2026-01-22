# Email Build Workflow

A systematic approach to building Kent State HTML email newsletters using module templates.

## Core Principle

**Extract, don't improvise.** All content comes directly from the wireframe. Never guess image paths, edit copy, or create content.

---

## Overview

```
Wireframe → Analyze → Build Module-by-Module → Validate → Deploy
```

Each newsletter is built by:
1. Identifying which modules are needed
2. Copying the appropriate template
3. Replacing placeholders with wireframe content
4. Assembling modules in order
5. Validating the final output

---

## Step 1: Setup

### Create Project Folder

```
projects/
└── [PROJECT_ID]/
    ├── wireframe.html      # From PM
    ├── reference.html      # Similar past email (optional)
    └── [PROJECT_ID].html   # Your output
```

### Extract Image Paths

Get all image references from the wireframe:

```bash
grep -o '[PROJECT_ID][^"<>]*\.\(jpg\|png\|gif\)' wireframe.html | sort -u
```

Save this list - you'll reference it for every module.

---

## Step 2: Analyze Wireframe

Open the wireframe and identify each content block:

| Look For | Maps To Module |
|----------|----------------|
| Large hero image + headline | `01_FEATURED_STORY` |
| Grey bar with section title | `02_SECTION_DIVIDER` |
| Two-column alternating images | `03_STORY_TILES` |
| Four stories in a grid | `04_2X2_STORIES` |
| Image left, text right | `05_STORY_BLOCK` |
| Calendar-style event list | `06_FEATURED_EVENTS` |
| Centered content on grey | `07_HERO_STORY` |
| Kent State header/footer | `00_WRAPPER_HEADER` / `09_FOOTER` |

### Create Module List

Document the build order:

```
1. Wrapper/Header
2. Featured Story (Giving Tuesday hero)
3. Spacer
4. Section Divider (Featured News)
5. Spacer
6. Story Tiles (2 stories)
7. Spacer
... etc
10. Footer
```

**Always add spacers** (`08_SPACER`) between major modules.

---

## Step 3: Build Module-by-Module

### For Each Module:

#### 3.1 Select Template

Open the appropriate `.txt` file from `/modules/`.

#### 3.2 Extract Content from Wireframe

**Images:** Copy exact path from wireframe HTML
```html
<!-- From wireframe -->
<img src="https://connect.kent.edu/www/images/26ALR148_PX_FEATURE_GT.png">

<!-- Use exactly as-is -->
```

**Text:** Copy verbatim - headlines, body text, button text
- Do not fix typos
- Do not improve wording
- Do not add punctuation

**URLs:** Extract `href` values exactly

#### 3.3 Replace Placeholders

Template placeholders follow this pattern:

| Placeholder | Replace With |
|-------------|--------------|
| `{{PROJECT_ID}}` | Project identifier (e.g., `26ALR148`) |
| `{{IMAGE_DESCRIPTOR}}` | Image suffix (e.g., `GT`, `Dean`) |
| `{{HEADLINE}}` | Exact headline from wireframe |
| `{{BODY_TEXT}}` | Exact body copy from wireframe |
| `{{CTA_URL}}` | Button destination URL |
| `{{CTA_TEXT}}` | Button text (e.g., "Read More") |
| `{{ALT_TEXT}}` | Image description for accessibility |

**Important:** Replace placeholders in BOTH MSO and non-MSO sections for buttons.

#### 3.4 Save Progress

Append completed module to your output file:
- First module: Start with `00_WRAPPER_HEADER`
- Subsequent modules: Append in order
- Final module: End with `09_FOOTER`

#### 3.5 Validate Module

Before moving on:
- [ ] Image path matches wireframe exactly
- [ ] Copy matches wireframe exactly
- [ ] URLs are correct
- [ ] MSO button matches standard button (URL + text)

---

## Step 4: Module-Specific Instructions

### Featured Story (`01_FEATURED_STORY`)

- Headline: **34px bold**, centered
- Full-width image (650px)
- CTA button below text
- Add clearing div after module

### Hero Story (`07_HERO_STORY`)

- Headline: **24px bold**, centered
- Grey background (#EAE9E5)
- ALL content centered
- Image width: 520px

### Story Block (`05_STORY_BLOCK`)

- Image: 240px, left column, `border-top-right-radius: 50px`
- Text: right column (375px)
- Headline: 24px bold

### Story Tiles (`03_STORY_TILES`)

- Two tiles per module
- Tile 1: Image RIGHT, text LEFT
- Tile 2: Image LEFT, text RIGHT
- No spacer between tiles in same module

### 2x2 Stories (`04_2X2_STORIES`)

- All 4 stories in ONE module
- Image width: 265px each
- `border-top-right-radius: 50px` on all images

### Featured Events (`06_FEATURED_EVENTS`)

Extract for each event:
- Month (3-letter: NOV, DEC)
- Day number
- Time
- Title
- URL
- Location

**"MORE EVENTS" link:** Left-aligned, blue (#0073bd), bold, double arrows (››)

---

## Step 5: Final Assembly

### Structure

```html
<!-- 00_WRAPPER_HEADER -->
[Header content]

<!-- ALL MODULES GO BELOW HERE -->

<!-- 01_FEATURED_STORY -->
[Featured content]

<!-- 08_SPACER -->
[Spacer]

<!-- 02_SECTION_DIVIDER -->
[Divider]

... more modules ...

<!-- 09_FOOTER -->
[Footer content]

<!-- Close wrapper tables -->
</td></tr></tbody></table>
</td></tr></tbody></table>
</body></html>
```

---

## Step 6: Validation

### Image Path Check

```bash
grep -o 'https://connect.kent.edu/www/images/[^"]*' [PROJECT_ID].html | sort -u
```

Compare with wireframe image list.

### Content Checklist

- [ ] All modules from wireframe implemented
- [ ] Image paths match wireframe exactly
- [ ] Copy matches wireframe exactly
- [ ] All links correct
- [ ] Spacers in correct locations
- [ ] MSO conditionals on ALL buttons
- [ ] Preheader div is empty

### Visual Check

Open in browser:
- [ ] All images load
- [ ] All links work
- [ ] Spacing looks consistent
- [ ] Colors match brand standards

---

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Hallucinated image names | Always extract from wireframe |
| Edited copy | Copy verbatim, including typos |
| Missing MSO conditional | Every button needs VML wrapper |
| Wrong headline size | Featured=34px, Hero/StoryBlock=24px |
| Plain text links for CTAs | Always use styled buttons |
| Coded divider lines | Use image dividers only |
| Split 2x2 stories | All 4 go in one module |

---

## File Naming

**Images:** `{{PROJECT_ID}}_PX_{{MODULE}}_{{DESCRIPTOR}}.jpg`

| Module | Prefix |
|--------|--------|
| Featured Story | `FEATURE` |
| Hero Story | `HERO` |
| Story Block | `STORYBLOCK` |
| Story Tile | `STORYTILE` |
| 2x2 Stories | `2x2` |

**Output:** `{{PROJECT_ID}}.html`

---

## Slate Envelope

Note these from wireframe for deployment:
- **Sender:** Name, Title | email@kent.edu
- **Reply-to:** email@kent.edu
- **Subject:** Full subject line
- **Preheader:** Preview text (set in Slate, not HTML)

Add Slate shortcut as HTML comment at top of file:
```html
<!-- SLATE SHORTCUT: https://connect.kent.edu/manage/deliver/mailing?id=GUID -->
```

---

*Workflow optimized for systematic, module-by-module building.*
