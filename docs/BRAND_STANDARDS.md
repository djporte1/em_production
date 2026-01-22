# Kent State Email Brand Standards

## Color Palette

| Color Name | Hex Code | Usage |
|------------|----------|-------|
| Kent Blue | `#003976` | Headings, button text, primary brand |
| Gold | `#EFAB00` | Buttons, accents, CTAs |
| Mid-Blue (OGE) | `#4994CB` | OGE-specific buttons |
| Grey | `#EAE9E5` | Backgrounds, dividers |
| White | `#FFFFFF` | Backgrounds, contrast |
| Body Text | `#101010` | Paragraph text |

## Typography

| Element | Font | Size | Weight | Color |
|---------|------|------|--------|-------|
| Featured Headline | Open Sans | 34px | Bold | Kent Blue (#003976) |
| Hero/Story Headline | Open Sans | 24px | Bold | Kent Blue (#003976) |
| Section Divider | Open Sans | 20px | Bold | Kent Blue (#003976) |
| Body Text | Open Sans | 18px | Normal | #101010 |
| Button Text | Open Sans | 18px | Bold | Kent Blue (#003976) |

**Font Stack:** `'Open+Sans', Arial, sans-serif`

## Button Styles

### Standard (Most Units)

| Property | Value |
|----------|-------|
| Background | Gold (#EFAB00) |
| Text | Kent Blue (#003976) |
| Font | 18px bold |
| Padding | 12px 24px |
| Corners | Square (0px radius) |

### OGE (Global Education)

| Property | Value |
|----------|-------|
| Background | Mid-Blue (#4994CB) |
| Text | White (#FFFFFF) |
| Font | 18px bold |
| Padding | 12px 24px |
| Corners | Square (0px radius) |

## Image Specifications

| Module Type | Width | Border Radius |
|-------------|-------|---------------|
| Featured Story | 650px (full width) | 0px |
| Hero Story | 650px (full width) | 0px |
| Story Block | 240px | 50px top-right |
| Story Tile | 295px | 50px top-right |
| 2x2 Stories | 265px each | 50px top-right |

**Image URL Base:** `https://connect.kent.edu/www/images/`

**Naming Convention:** `{{PROJECT_ID}}_PX_{{MODULE}}_{{DESCRIPTOR}}.jpg`

Examples:
- `26ALR148_PX_FEATURE_GT.png`
- `26DIA195_PX_STORYBLOCK_Kinicki.jpg`
- `26CEH018_PX_STORYTILE_Dean.jpg`

## Divider Lines

**Always use image dividers, never coded bgcolor dividers.**

| Unit | Divider Image URL |
|------|-------------------|
| Standard (Gold) | `https://connect.kent.edu/www/images/dividerbar_EFAB00.png` |
| OGE (Mid-Blue) | `https://connect.kent.edu/www/images/dividerbar_4994CB.png` |

```html
<!-- CORRECT -->
<tr>
  <td align="center" style="padding:20px 0;">
    <img src="https://connect.kent.edu/www/images/dividerbar_EFAB00.png" alt="" width="600" />
  </td>
</tr>

<!-- WRONG - Never do this -->
<tr><td bgcolor="#EFAB00" height="3"></td></tr>
```

## MSO Conditionals (Outlook)

**Required for every CTA button.** Outlook doesn't render CSS buttons properly.

```html
<!--[if mso]>
<table align="center" border="0" cellspacing="0" cellpadding="0">
  <tr>
    <td align="center">
      <v:roundrect xmlns:v="urn:schemas-microsoft-com:vml"
                   xmlns:w="urn:schemas-microsoft-com:office:word"
                   href="{{URL}}"
                   style="height:50px;v-text-anchor:middle;width:220px;"
                   arcsize="0%" stroke="f" fillcolor="#EFAB00">
        <w:anchorlock/>
        <center style="color:#003976;font-family:Arial,sans-serif;font-size:18px;font-weight:bold;">
          {{CTA_TEXT}}
        </center>
      </v:roundrect>
    </td>
  </tr>
</table>
<![endif]-->

<!--[if !mso]><!-- -->
<!-- Standard HTML button here -->
<!--<![endif]-->
```

## Responsive Classes

| Class | Purpose | Mobile Behavior |
|-------|---------|-----------------|
| `.wrapper` | Max-width container | `width: 100%` |
| `.hide` | Desktop-only elements | `display: none` |
| `.full_img` | Responsive images | `width: 100%` |
| `.mobile` | Text adjustments | Center-aligned |
| `.pad_side` | Side padding | 14px left/right |
| `.fix_height` | Fixed height spacers | 20px on mobile |

## Inline Text Formatting

### Bullet Lists

Use proper HTML `<ul><li>` structure:

```html
<ul style="padding-left:30px; margin:0;">
  <li style="padding-bottom:5px;">
    <span style="font-family:'Open+Sans',Arial,sans-serif; font-weight:bold; font-size:18px; color:#101010;">
      Main Point
    </span>
  </li>
</ul>
```

**Do NOT use:** `&#8226;` entities, CSS `list-style-type`, or text bullets.

### Underlined Links

Force underlines in all clients:

```html
<a href="URL" style="color:#003976; text-decoration:underline !important; font-weight:bold;">
  <u>link text</u>
</a>
```

Use both CSS `text-decoration` AND the `<u>` tag for maximum compatibility.

---

*Reference: Kent State University Brand Guidelines*
