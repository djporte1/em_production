# Newsletter Module Templates Reference

Quick reference for all implemented module types with visual descriptions, field requirements, and examples.

---

## Template Index

1. [Storyblock](#storyblock) - Image left, content right
2. [Storyblock No Image](#storyblock-no-image) - Centered text only
3. [Featured](#featured) - Full-width hero with overlay
4. [Hero](#hero) - Grey background centered story
5. [Storytile Right](#storytile-right) - Image right, text left
6. [Storytile Left](#storytile-left) - Image left, text right
7. [2x2 Stories](#2x2-stories) - Four-story grid
8. [Divider](#divider) - Section header bar
9. [Spacer](#spacer) - Vertical spacing

---

## Storyblock

### Visual Structure
```
┌────────────────────────────────────┐
│  ┌─────┐  Title                    │
│  │     │  Description text here... │
│  │IMG  │  Lorem ipsum dolor sit... │
│  │240px│  [Button]                 │
│  └─────┘                           │
└────────────────────────────────────┘
```

### Module Type
`"type": "storyblock"`

### Use Cases
- Dean's messages
- Faculty spotlights
- Feature stories with headshots
- Any content with side image

### Required Fields
```json
{
  "type": "storyblock",
  "bgcolor": "#FFFFFF",           // or "#EAE9E5" for grey
  "image": "filename.jpg",         // 240px width optimal
  "title": "Story Title",
  "description": "Full story text...",
  "button_text": "Read More",
  "button_url": "https://example.com"
}
```

### Image Specifications
- **Width**: 240px
- **Style**: `border-top-right-radius: 50px` (rounded corner)
- **Format**: JPG recommended
- **Alt text**: Derived from title

### Example
```json
{
  "01_01_storyblock_dean": {
    "type": "storyblock",
    "bgcolor": "#FFFFFF",
    "image": "25CAE023_PX_STORYBLOCK_Bloebaum.jpg",
    "title": "Advancing Aeronautics and Engineering",
    "description": "Greetings from the College of Aeronautics and Engineering! The momentum across our college continues to build...",
    "button_text": "Visit Our Website",
    "button_url": "https://www.kent.edu/cae"
  }
}
```

---

## Storyblock No Image

### Visual Structure
```
┌────────────────────────────────────┐
│          Title Centered            │
│    Description text centered...    │
│         [Button]                   │
└────────────────────────────────────┘
```

### Module Type
`"type": "storyblock_no_image"`

### Use Cases
- Announcements without photos
- Calls to action
- Event nominations
- Text-focused messages

### Required Fields
```json
{
  "type": "storyblock_no_image",
  "bgcolor": "#EAE9E5",           // or "#FFFFFF"
  "title": "Announcement Title",
  "description": "Full announcement text...",
  "button_text": "Learn More",
  "button_url": "https://example.com"
}
```

### Example
```json
{
  "25_25_storyblock_envision": {
    "type": "storyblock_no_image",
    "bgcolor": "#EAE9E5",
    "title": "Accepting Nominations for Envision Awards",
    "description": "The College of Aeronautics and Engineering will recognize outstanding, notable and accomplished alumni...",
    "button_text": "Learn More",
    "button_url": "https://www.kent.edu/cae/envision-awards"
  }
}
```

---

## Featured

### Visual Structure
```
┌────────────────────────────────────┐
│                                    │
│     ┌──────────────────────┐      │
│     │                      │      │
│     │    HERO IMAGE 650px  │      │
│     │                      │      │
│     └──────────────────────┘      │
│                                    │
│          Feature Title             │
│    Feature description text...     │
│         [Gold Button]              │
└────────────────────────────────────┘
```

### Module Type
`"type": "featured"`

### Use Cases
- Major announcements
- Headline stories
- Landing features
- High-impact visuals

### Required Fields
```json
{
  "type": "featured",
  "image": "filename.jpg",         // 650px width
  "title": "Feature Title",
  "description": "Feature story text with multiple paragraphs supported via \\n",
  "button_text": "Read More",
  "button_url": "https://example.com"
}
```

### Image Specifications
- **Width**: 650px (full content width)
- **Height**: Flexible (typically 350-450px)
- **Format**: JPG
- **Style**: No border radius
- **Position**: Above text content

### Example
```json
{
  "03_03_featured_two_schools": {
    "type": "featured",
    "image": "26CAE030_PX_FEATURE_RecordGrowth.jpg",
    "title": "College of Aeronautics and Engineering Forms Two Schools Amid Record Growth",
    "description": "In response to unprecedented growth and expanding academic offerings, Kent State's College of Aeronautics and Engineering has announced the formal establishment of two distinct academic units...",
    "button_text": "Read More",
    "button_url": "https://www.kent.edu/cae/news/kent-state-college-aeronautics-and-engineering-announces-formation-two-schools-amid-record"
  }
}
```

---

## Hero

### Visual Structure
```
┌────────────────────────────────────┐
│     GREY BACKGROUND (#EAE9E5)      │
│                                    │
│     ┌──────────────────────┐      │
│     │    IMAGE 650px       │      │
│     └──────────────────────┘      │
│                                    │
│          Story Title               │
│    Story description centered...   │
│         [Gold Button]              │
│                                    │
└────────────────────────────────────┘
```

### Module Type
`"type": "hero"`

### Use Cases
- Important stories
- Event highlights
- Campus visits
- Official announcements

### Required Fields
```json
{
  "type": "hero",
  "image": "filename.jpg",         // 650px width
  "title": "Hero Story Title",
  "description": "Story description...",
  "button_text": "Read More",
  "button_url": "https://example.com"
}
```

### Image Specifications
- **Width**: 650px
- **Background**: Grey (#EAE9E5)
- **Format**: JPG
- **Style**: No border radius
- **Position**: Top, above centered text

### Example
```json
{
  "07_07_hero_lt_governor": {
    "type": "hero",
    "image": "26CAE030_PX_HERO_Tressel.jpg",
    "title": "Ohio Lt. Governor Tours College of Aeronautics and Engineering",
    "description": "Ohio Lt. Gov. Jim Tressel recently toured the College of Aeronautics and Engineering to see firsthand how the university is educating students...",
    "button_text": "Read More",
    "button_url": "https://www.kent.edu/today/news/flying-high-ohios-lieutenant-governor-tours-kent-states-nationally-ranked-college"
  }
}
```

---

## Storytile Right

### Visual Structure
```
┌────────────────────────────────────┐
│  Title              ┌────────┐     │
│  Description...     │        │     │
│  Lorem ipsum...     │  IMG   │     │
│  [Button]           │  295px │     │
│                     └────────┘     │
└────────────────────────────────────┘
```

### Module Type
`"type": "storytile_right"`

### Use Cases
- News briefs
- Article previews
- Research highlights
- Multi-story sections (alternate with storytile_left)

### Required Fields
```json
{
  "type": "storytile_right",
  "image": "filename.jpg",         // 295px width
  "title": "Story Title",
  "description": "Brief story description...",
  "button_text": "Read More",
  "button_url": "https://example.com"
}
```

### Image Specifications
- **Width**: 295px
- **Style**: `border-top-right-radius: 50px`
- **Position**: Right side
- **Format**: JPG

### Example
```json
{
  "09_09_storytile_satellites": {
    "type": "storytile_right",
    "image": "26CAE030_PX_STORYTILE_Satellites.jpg",
    "title": "Students Build Flight-ready Satellites",
    "description": "Students in the AstroFlashes space exploration club are designing, building and testing satellites...",
    "button_text": "Read More",
    "button_url": "https://www.kent.edu/today/news/kent-states-spacecraft-design-lab-where-students-build-flight-ready-satellites"
  }
}
```

---

## Storytile Left

### Visual Structure
```
┌────────────────────────────────────┐
│  ┌────────┐         Title          │
│  │        │  Description text...   │
│  │  IMG   │  Lorem ipsum dolor...  │
│  │  295px │  [Button]              │
│  └────────┘                        │
└────────────────────────────────────┘
```

### Module Type
`"type": "storytile_left"`

### Use Cases
- Same as storytile_right
- Alternate for visual variety
- Create zig-zag pattern with storytile_right

### Required Fields
Same as storytile_right

### Image Specifications
Same as storytile_right, but positioned left

### Example
```json
{
  "11_11_storytile_airport": {
    "type": "storytile_left",
    "image": "26CAE030_PX_STORYTILE_Airport.jpg",
    "title": "FAA Grant Supports Airport Infrastructure",
    "description": "A $4.1 million FAA grant will fund major infrastructure upgrades at the Kent State Airport...",
    "button_text": "Read More",
    "button_url": "https://www.kent.edu/cae/news/faa-grant-kent-state-airport-enhances-student-training-and-supports-workforce-needs"
  }
}
```

---

## 2x2 Stories

### Visual Structure
```
┌──────────────────────────────────────┐
│  ┌─────────┐      ┌─────────┐       │
│  │ IMG 265 │      │ IMG 265 │       │
│  │         │      │         │       │
│  └─────────┘      └─────────┘       │
│  Story 1 Title    Story 2 Title     │
│  Description...   Description...    │
│  [Button]         [Button]          │
│                                      │
│  ┌─────────┐      ┌─────────┐       │
│  │ IMG 265 │      │ IMG 265 │       │
│  │         │      │         │       │
│  └─────────┘      └─────────┘       │
│  Story 3 Title    Story 4 Title     │
│  Description...   Description...    │
│  [Button]         [Button]          │
└──────────────────────────────────────┘
```

### Module Type
`"type": "2x2_stories"`

### Use Cases
- Student profiles
- Multiple related stories
- Alumni spotlights
- Team introductions

### Required Fields
```json
{
  "type": "2x2_stories",
  "stories": [
    {
      "image": "story1.jpg",         // 265px width each
      "title": "Story 1 Title",
      "description": "Story 1 description...",
      "button_text": "Read More",
      "button_url": "https://example.com/story1"
    },
    {
      "image": "story2.jpg",
      "title": "Story 2 Title",
      "description": "Story 2 description...",
      "button_text": "Read More",
      "button_url": "https://example.com/story2"
    },
    {
      "image": "story3.jpg",
      "title": "Story 3 Title",
      "description": "Story 3 description...",
      "button_text": "Read More",
      "button_url": "https://example.com/story3"
    },
    {
      "image": "story4.jpg",
      "title": "Story 4 Title",
      "description": "Story 4 description...",
      "button_text": "Read More",
      "button_url": "https://example.com/story4"
    }
  ]
}
```

### Image Specifications
- **Width**: 265px each (4 images)
- **Style**: `border-top-right-radius: 50px`
- **Layout**: 2 columns × 2 rows
- **Format**: JPG

### Example
```json
{
  "23_23_2x2_student_stories": {
    "type": "2x2_stories",
    "stories": [
      {
        "image": "26CAE030_PX_2x2_Experience.jpg",
        "title": "Building Experience",
        "description": "Opportunities at Kent State are giving Stuart Klein, a junior aerospace engineering major, a front-row seat...",
        "button_text": "Read More",
        "button_url": "https://www.kent.edu/cae/news/building-experience-through-research-and-leadership"
      },
      {
        "image": "26CAE030_PX_2x2_Dreams.jpg",
        "title": "Dreams Take Flight",
        "description": "Philip Hirst, a junior aeronautics major with a concentration in unmanned aircraft systems...",
        "button_text": "Read More",
        "button_url": "https://www.kent.edu/admissions/news/my-dreams-have-truly-taken-flight"
      },
      {
        "image": "26CAE030_PX_2x2_Success.jpg",
        "title": "Flight Path to Success",
        "description": "When Jackson Polcyn, a senior majoring in aeronautics with a concentration in air traffic control...",
        "button_text": "Read More",
        "button_url": "https://www.kent.edu/admissions/news/flight-path-future-success"
      },
      {
        "image": "26CAE030_PX_2x2_Future.jpg",
        "title": "Into the Future",
        "description": "From high school internships to hands-on rotations with Goodyear, Angel Guinn, a senior majoring in mechatronics engineering...",
        "button_text": "Read More",
        "button_url": "https://www.kent.edu/admissions/news/out-frying-pan-future"
      }
    ]
  }
}
```

---

## Divider

### Visual Structure
```
┌────────────────────────────────────┐
│                                    │
│      Section Title Text            │
│                                    │
└────────────────────────────────────┘
       Grey background bar
```

### Module Type
`"type": "divider"`

### Use Cases
- Section headers
- Content separators
- Topic transitions

### Required Fields
```json
{
  "type": "divider",
  "text": "Section Title"
}
```

### Styling
- **Background**: Grey (#EAE9E5)
- **Text**: Kent Blue (#003976)
- **Font**: Open Sans, 24px, bold
- **Height**: ~40px
- **Alignment**: Center

### Example
```json
{
  "05_05_divider_featured_news": {
    "type": "divider",
    "text": "Featured News"
  },
  "17_17_divider_student_success": {
    "type": "divider",
    "text": "Student Success"
  }
}
```

---

## Spacer

### Visual Structure
```
┌────────────────────────────────────┐
│                                    │
│         (22px empty space)         │
│                                    │
└────────────────────────────────────┘
```

### Module Type
`"type": "spacer"`

### Use Cases
- Between ALL content modules
- Vertical spacing
- Visual breathing room

### Required Fields
```json
{
  "type": "spacer"
}
```

### Specifications
- **Height**: 22px (20px + padding)
- **No background**
- **No borders**
- **Collapses on mobile** (optional via class)

### Usage Pattern
**Always insert spacers between modules**:
```json
{
  "01_01_content": { "type": "storyblock", ... },
  "02_02_spacer": { "type": "spacer" },
  "03_03_content": { "type": "featured", ... },
  "04_04_spacer": { "type": "spacer" },
  "05_05_content": { "type": "hero", ... },
  "06_06_spacer": { "type": "spacer" }
}
```

---

## Brand Standards

### Color Palette

| Color Name | Hex Code | Usage |
|------------|----------|-------|
| Kent Blue | `#003976` | Headings, button text, primary brand |
| Gold | `#EFAB00` | Buttons, accents, CTAs |
| Grey | `#EAE9E5` | Backgrounds, dividers |
| White | `#FFFFFF` | Backgrounds, contrast |
| Black | `#101010` | Body text |

### Typography

| Element | Font | Size | Weight | Color |
|---------|------|------|--------|-------|
| H1 (Titles) | Open Sans | 24px | Bold | Kent Blue (#003976) |
| Body Text | Open Sans | 18px | Normal | Black (#101010) |
| Button Text | Open Sans | 18px | Bold | Kent Blue (#003976) |
| Divider Text | Open Sans | 24px | Bold | Kent Blue (#003976) |

### Button Styles

```css
Background: Gold (#EFAB00)
Text: Kent Blue (#003976)
Font: Open Sans, 18px, Bold
Padding: 12px 24px
Border Radius: 0px (square)
```

### Image Guidelines

| Module Type | Width | Height | Format | Border Radius |
|-------------|-------|--------|--------|---------------|
| Storyblock | 240px | Auto | JPG | 50px top-right |
| Featured | 650px | Auto | JPG | 0px |
| Hero | 650px | Auto | JPG | 0px |
| Storytile | 295px | Auto | JPG | 50px top-right |
| 2x2 Stories | 265px | Auto | JPG | 50px top-right |

**URL Format**: `https://connect.kent.edu/www/images/{filename}`

---

## Mobile Responsive Classes

### Key Classes

| Class | Purpose | Behavior |
|-------|---------|----------|
| `.hide` | Hide on mobile | `display: none` at <600px |
| `.full_img` | Responsive images | `width: 100%` on mobile |
| `.mobile` | Mobile text adjustments | Font size scales |
| `.pad_side` | Side padding | Adjusts for mobile width |
| `.wrapper` | Max-width container | Centers content |
| `.pad_top` | Top padding on mobile | Extra spacing |
| `.fix_height` | Fixed height elements | May adjust on mobile |

---

## MSO Conditionals (Outlook)

All templates include Outlook-specific code:

```html
<!--[if mso]>
<v:roundrect xmlns:v="urn:schemas-microsoft-com:vml"
             href="URL"
             style="height:50px;v-text-anchor:middle;width:220px;"
             arcsize="0%"
             stroke="f"
             fillcolor="#EFAB00">
  <w:anchorlock/>
  <center style="color:#003976;font-family:Arial,sans-serif;font-size:18px;font-weight:bold;">
    Button Text
  </center>
</v:roundrect>
<![endif]-->
```

**DO NOT REMOVE** - Required for button rendering in Outlook

---

## Quick Reference Checklist

### Pre-Build
- [ ] Analyzed wireframe and identified all modules
- [ ] Created build_plan.json with all modules
- [ ] Added spacers between every module
- [ ] Used double-numbered naming (01_01, 02_02, etc.)
- [ ] Verified all image filenames

### During Build
- [ ] Ran `python3 02_generate_modules.py`
- [ ] Checked `modules/` directory for all files
- [ ] Verified module count matches expectation
- [ ] Ran `python3 03_assemble.py`
- [ ] Checked final line count

### Post-Build
- [ ] Validated HTML structure
- [ ] Verified all images use correct URL format
- [ ] Tested in Gmail, Outlook, Apple Mail
- [ ] Checked mobile responsive behavior
- [ ] Validated all links return 200

---

## Common Patterns

### Alternating Storytiles
```json
"09_storytile_1": { "type": "storytile_right", ... },
"10_spacer": { "type": "spacer" },
"11_storytile_2": { "type": "storytile_left", ... },
"12_spacer": { "type": "spacer" },
"13_storytile_3": { "type": "storytile_right", ... },
"14_spacer": { "type": "spacer" },
"15_storytile_4": { "type": "storytile_left", ... }
```

### Section Structure
```json
"05_divider": { "type": "divider", "text": "Section Name" },
"06_spacer": { "type": "spacer" },
"07_content": { "type": "storyblock", ... },
"08_spacer": { "type": "spacer" },
"09_content": { "type": "storyblock", ... }
```

### Opening/Closing Pattern
```json
"01_opening": { "type": "storyblock", ... },      // Dean's message
"02_spacer": { "type": "spacer" },
...                                                 // Middle content
"26_spacer": { "type": "spacer" },
"27_closing": { "type": "storyblock", ... }        // Support/CTA
```

---

**Template Reference Version**: 1.0
**Last Updated**: 2025-10-14
**Status**: Complete - All 9 module types documented
