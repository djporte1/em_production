# Email QA Checklist

Run through this after every email build before sending for review.

---

## Template Fidelity

- [ ] **Used correct module template** from `/modules/` - don't improvise structure
- [ ] **Featured Story headline** = 34px bold
- [ ] **Hero Story headline** = 24px bold, body text CENTERED
- [ ] **Story Block columns** = 230px left (float:left), 375px right (float:right), image 240px
- [ ] **Story Block image** has `border-top-right-radius: 50px`
- [ ] **Clearing div** after Featured modules: `<div style="display:block; height:0; line-height:0; font-size:0; clear:both;"></div>`

---

## CTAs & Links

- [ ] **All CTAs are styled buttons** (gold #EFAB00, blue text #003976) - NO plain text links
- [ ] **MSO conditional** on every CTA button (VML roundrect wrapper)
- [ ] **Both MSO and standard button** have correct URL
- [ ] **Image links** point to correct destination (check all `<a href>` wrapping images)

---

## Images

- [ ] **Alt tags** on ALL images - descriptive, not empty
- [ ] **Image paths** extracted from wireframe - never guessed/hallucinated
- [ ] **Image widths** match template specs (Feature=full width, Hero=520px, Story Block=240px)

---

## Content

- [ ] **Preheader div is EMPTY** - preheader set in Slate, not HTML
- [ ] **Copy matches wireframe exactly** - no edits/rewrites
- [ ] **Merge fields** correct: `{{Person-Preferred}}`, `{{Person-GUID}}`, etc.

---

## Footer

- [ ] **Correct college/department** header image and link
- [ ] **Social accounts** match college (ksualumni, KentCPH, kentstateehhs, kentnursing, thegoldenflashesclub)
- [ ] **Contact info** correct (email, phone vary by college)
- [ ] **Footer links** correct:
  - Standard: Update Your Information | Make a Gift | Visit Our Site
  - DIA: Update Sport Preferences | Make a Gift | Visit Our Site
    - Update Sport Preferences URL: `https://connect.kent.edu/register/athletics-preferences?person={{Person-GUID}}`
    - Make a Gift URL: `https://flashes.givetokent.org/campaign/kent-state-athletics/c390897`
    - Visit Our Site URL: `https://kentstatesports.com/`

---

## College Quick Reference

| College | Email | Phone | Social |
|---------|-------|-------|--------|
| ALR | alumni@kent.edu | 330-672-5368 | ksualumni |
| CEH | ehhsdean@kent.edu | 330-672-2202 | kentstateehhs |
| CON | nursing@kent.edu | 330-672-7930 | kentnursing |
| CPH | publichealth@kent.edu | 330-672-6500 | KentCPH |
| DIA | thegoldenflashesclub@kent.edu | 330-672-2078 | thegoldenflashesclub |

---

## Proofreading (separate pass)

- [ ] **Read all body copy aloud** - catches awkward phrasing
- [ ] **Check names/titles** - spelled correctly, credentials accurate
- [ ] **Dates/times** - day of week matches date, AM/PM correct
- [ ] **Dollar amounts** - commas, decimal places
- [ ] **URLs** - no typos in display text (hover to verify actual links)
- [ ] **Headlines** - no truncation, proper capitalization

---

## Final Validation

- [ ] **Open in browser** - visual check for layout issues
- [ ] **Ctrl+F "{{" ** - verify all merge fields are intentional
- [ ] **Ctrl+F "XXX"** - catch any placeholder image names
- [ ] **Compare to reference template** if one was provided

---

## Slate Envelope (note for handoff)

Extract from wireframe:
- Sender:
- Reply-to:
- Subject:
- Preheader:

---

*Last updated: December 2025*
