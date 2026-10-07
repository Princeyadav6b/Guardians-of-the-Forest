# Guardians of the Forest

**Role of Tribal Communities in Protecting Forests and Natural Resources**

A premium, responsive, single-page educational website built for a first-year university
Environmental Studies project at Lovely Professional University.

This guide explains (1) what is in the folder, (2) how to open and publish the site, and
(3) **exactly which placeholders to replace** before submission.

---

## 1. What is in this folder

```
index.html                              The whole website (one page, semantic HTML, all sections)
assets/
  css/style.css                         The design system (colours, typography, layout, responsive)
  js/main.js                            Navigation, scroll, map, share/copy, video player
  img/                                  Six AI visuals + your documentary thumbnail
guardians-of-the-forest-single-file.html  Same site with everything inlined (works with no server)
README.md                               This guide
```

**No build step, no dependencies, no external requests.** The only external links are the
source citations (Census of India, Ministry of Tribal Affairs, and so on). The site works
offline by double-clicking `index.html`; everything except YouTube embeds and outbound
citation links works from a local file too.

The full India outline used in the interactive map and the case-study location map is
embedded directly in the HTML as an SVG path — there is nothing to load and nothing to
break. The outline geometry is adapted from the open-source **Mapsicon** set (MIT licence),
which is credited in the Sources section.

---

## 2. How to open and publish

**Preview locally:** double-click `index.html` (or right-click → Open with your browser).

**Publish (free options):** drag the folder onto Netlify Drop, use GitHub Pages, or upload
to any web host. Keep the folder structure exactly as it is (`index.html` next to `assets/`).

**After publishing, update three lines in the `<head>` of `index.html`** so social-media
previews work correctly:

| Line | Replace with |
|---|---|
| `<link rel="canonical" href="[PASTE PUBLISHED PAGE URL HERE]">` (currently commented out) | your live page URL, uncomment the line |
| `<meta property="og:url" content="[PASTE PUBLISHED PAGE URL HERE]">` | your live page URL |
| `<meta property="og:image" content="assets/img/documentary-poster.jpg">` | the **absolute** URL, e.g. `https://your-site.netlify.app/assets/img/documentary-poster.jpg` |

---

## 3. Placeholder checklist (replace everything below)

Use your editor's **Find** (Ctrl/Cmd + F) on `index.html`. Every bracketed placeholder is
in square brackets so it is easy to spot.

### 3.1 Documentary video — ✅ DONE
Your YouTube link is installed: **<https://youtu.be/iohFZNng-O8>** (in the Documentary
section as `data-video-url`, in the "Watch on YouTube" button, in the footer, and in the
bibliography). The poster image is your own documentary thumbnail
(`assets/img/documentary-poster.jpg`).

The player stays as a poster until a visitor presses **Play** — nothing autoplays, and the
page stays fast.

> ### About the "This content is blocked" message
> YouTube refuses to load its player in two situations, and both are **environment problems,
> not faults in your site**:
>
> 1. **Opened straight from a file** (`file://`) — there is no web address to send as a referrer.
> 2. **Inside a sandboxed preview pane** (like an in-app preview). Browsers give such frames an
>    opaque `null` origin, and YouTube blocks playback for them.
>
> The site now detects both cases and shows its own clean panel with a gold **"Watch on YouTube"**
> button and the direct link (`youtu.be/iohFZNng-O8`) instead of YouTube's error box.
> **On the published website the player loads normally inside the page** — verified by testing
> the same page through a normal web address, where your video plays in-page as expected.
>
> **How to see the in-page player while you work:** publish the site, or run a local server.
> In your project folder run `python3 -m http.server 8000` and open
> `http://localhost:8000/index.html`.

### 3.2 Team details — ✅ DONE
| Member | Registration number | Role |
|---|---|---|
| **Prince Kumar** | 12601479 | Research, introduction, and narration |
| **Reeyana Kompirili** | 12617363 | Traditional knowledge, challenges, solutions, and narration |
| **Badarla Prem Sai Venkata Durga Manikanta** | 12625806 | Conservation practices, legal research, case study, and narration |

Course: **B.Tech CSE (Robotics and AI)** · Section: **K3P26AV** · Institution: Lovely Professional University

Names also appear in the footer team list. Only the **photographs** remain to be added
(three `[UPLOAD PHOTO]` placeholders in the team cards).

### 3.3 Photographs
The team cards, the eight gallery tiles, and the five campaign screenshots currently show
labelled placeholders. To insert a real photograph in the **team cards**, replace this block:

```html
<span class="member__photo-ph" role="img" aria-label="Placeholder for a photograph of team member one">
  <svg class="ico ico--xl" aria-hidden="true"><use href="#i-upload"></use></svg>
  <span class="member__photo-note">[UPLOAD PHOTO]</span>
</span>
```

with:

```html
<img src="assets/img/team-1.jpg" alt="Photograph of <name>, project team member" width="600" height="600" loading="lazy" decoding="async">
```

For the **gallery**, replace the whole `<span class="tile__frame">…</span>` block with an
`<img>` of the same shape, keeping the caption paragraph underneath. Always keep the image
cropped roughly square for team photos and 4:3 for gallery tiles.

> Only use photographs you took or have permission to use. **Never** use photos of tribal
> community members without their informed consent, and never download random images of
> tribal communities from the internet to illustrate this project.

### 3.4 Social-media links — partly done
YouTube and Instagram in the footer are now **real links** (to the documentary and the reel).
Two buttons remain as reminders — WhatsApp and X. Turn each into a real link when you have
the account:

```html
<li>
  <a class="social" href="https://www.youtube.com/@your-channel" target="_blank" rel="noopener noreferrer">
    <svg class="ico" aria-hidden="true"><use href="#i-youtube"></use></svg> YouTube
  </a>
</li>
```

Delete the `data-placeholder="…"` attribute when you convert a button to a link, otherwise
the reminder message will keep appearing.

### 3.5 Awareness-campaign figures — ✅ RECORDED (Instagram reel)
As supplied by the team, the campaign section now shows:

| Metric | Value |
|---|---|
| Campaign link | <https://www.instagram.com/reel/DeKDAlZyRiY/> |
| Likes | 110 |
| Comments | 19 |
| Shares | 67 |
| Date recorded | 07 October 2026 |

The **YouTube Views** row was replaced with the Instagram reel link, as requested. **No
YouTube view count is shown** because none was recorded — the page states this openly rather
than guessing. If you later read the YouTube view count and its date, add a new metric card
with that number.

Still to do here: swap the five screenshot placeholders (`[UPLOAD SCREENSHOT]`,
`[VIEWS / LIKES SCREENSHOT]`, `[COMMENTS SCREENSHOT]`, `[INSIGHTS SCREENSHOT]`,
`[PROMOTION SCREENSHOT]`) for real screenshots — blur any personal information first.

### 3.6 Sources and further reading
The Sources section already contains six verified, real references (Census of India 2011;
Ministry of Tribal Affairs; Forest Rights Act, 2006; India State of Forest Report 2023;
FAO reports; UN 2030 Agenda; plus the Mendha-Lekha press and field reports). Replace the
remaining `[ADD …]` entries with the full APA-style references from your own literature
review. Suggested formats are shown in brackets — keep the style consistent:

> Author, A. A. (Year). *Title of work*. Publisher. https://doi.org/…

Do **not** invent authors, dates, statistics, quotations, or links. If a statistic appears
anywhere on the page, its source must appear next to it.

### 3.7 Optional extras
- `[ADD GOVERNMENT SOURCE …]`, `[ADD JOURNAL ARTICLE …]`, `[ADD BOOK …]`,
  `[ADD INTERNATIONAL REPORT …]`, `[ADD VISUAL SOURCE …]` — bibliography slots.
- The documentary section has a row labelled **Note** for the upload date and platform.

---

## 4. Facts used on the site (all with visible sources)

| Statement | Source cited on the page |
|---|---|
| Documentary and awareness reel | The team's own published links (YouTube <https://youtu.be/iohFZNng-O8>, Instagram reel) |
| Campaign engagement: 110 likes, 19 comments, 67 shares, recorded 07 October 2026 | Read from the team's own Instagram reel; the page states these were team-recorded and will change over time |
| ~10.42 crore Scheduled Tribe population; ~8.6% of India's population | Census of India 2011 |
| Forest cover 21.76% of geographical area; bamboo-bearing area, 18th assessment | India State of Forest Report 2023 (Forest Survey of India) |
| Mendha-Lekha received community forest rights over ~1,809 ha in 2009; Gram Sabha rules on protection, grazing, monitoring, bamboo | Public field reports and press coverage (Business Today, Centre for Science and Environment, Institute of Community Forest Governance) |
| SDG names and numbers (6, 13, 15, 16) | United Nations, 2030 Agenda |

The **illustrative map** is deliberately described as approximate: the highlighted belts are
overlapping circles clipped to a real India outline. They are educational context, not
community territories or legal boundaries. This is stated on the page and in the caption.

Every image is an **AI-generated educational reconstruction** and is labelled as such, as
required by the project brief.

---

## 5. Editing tips

- **Colours, spacing, fonts:** all in the `:root { … }` block at the top of `assets/css/style.css`.
  Changing `--forest-900`, `--gold`, `--beige` and friends restyles the whole site consistently.
- **Section order:** sections are independent `<section>` blocks in `index.html`; you can move
  one by cutting and pasting the whole block. Navigation links point to ids (`#knowledge`,
  `#groves`, …), which move with the block.
- **Adding a card:** copy an existing `<li class="card reveal">` and edit the icon reference
  (`<use href="#i-leaf">`). All icons are inline SVG symbols at the top of the page — add a
  new `<symbol id="i-name">` to create a new icon.
- **Reduced motion:** animations switch themselves off automatically for visitors who set
  "reduce motion" in their operating system.

## 6b. Two versions of the site — keep them in sync

- **`index.html` + `assets/`** — the master copy. Edit this one, and use it for submission/hosting.
- **`guardians-of-the-forest-single-file.html`** — everything inlined into one file (≈1.95 MB).
  It needs no server and no network, which makes it handy for a quick look. It is a *copy*:
  changes made here will be lost the next time it is regenerated.
  Ask your assistant to regenerate it after editing the master, or rebuild it yourself by
  inlining `assets/css/style.css`, `assets/js/main.js` and the images as data URIs.

## 6. Accessibility and technical notes (already implemented)

- Skip-to-content link, keyboard-operable menus, visible focus outlines, `aria-expanded`
  states, `aria-pressed` map buttons, live region for updates, and a described illustrative
  map for screen readers.
- Semantic landmarks (`header`, `nav`, `main`, `section`, `footer`), a single `h1`, and
  ordered headings.
- Lazy-loaded images and video, fixed image dimensions (no layout shift), one CSS and one JS
  file, and no external requests — the page is fast and works offline.
- No autoplaying audio or video anywhere. The YouTube iframe is created only after a click.
- Print stylesheet included, so the page prints as a clean handout.

---

## 7. Credits and licences

- **Website and documentary:** student project team (add your names above).
- **Illustrations:** AI-generated for this educational project using image-generation tools,
  prompted to avoid stereotypical or ceremonial representations. They do not depict real
  individuals.
- **India outline:** adapted from **Mapsicon** by Djaiss (MIT licence) —
  <https://github.com/djaiss/mapsicon>. Credit is included in the Sources section.
- **Typefaces:** system fonts only (Iowan Old Style / Palatino / Georgia for headings and the
  platform UI font for body text). Nothing is downloaded, so there are no font licences to
  manage and no tracking.
