# Offline HTML Siddur - סידור

A single-file, offline Hebrew siddur that runs in any browser. No JavaScript, no network
requests, no dependencies — the fonts and the full text are embedded directly in the HTML,
so it works on kosher phones, dumbphones, and anything else with a browser.

**`index.html` is the current build.** It merges the two source builds below: the full
iVelt-derived text (38 sections, ~2,600 paragraphs of pointed Nusach Sefard) with the
warmer parchment color scheme of the Metsudah-based build, and adds a navigation layer on
top — all still without a single line of JavaScript.
 
## Credits and origin
 
This is an adaptation. It is not original work, and the people below did the part that
actually matters — digitizing, typesetting, and assembling the text.
 
**Original siddur — קנאפער ידען (Knaper Yidden) on iVelt**
The underlying siddur was built and posted on the iVelt forum.
<https://www.ivelt.com/forum/memberlist.php?mode=viewprofile&u=5372>
 
**Dumbphone HTML version — "Sams Club" on JTech Forums**
Repackaged as a self-contained HTML file for MindPhone and other kosher phones, and shared
in the thread *Complete Siddur HTML for Dumbphones*.
<https://forums.jtechforums.org/t/complete-siddur-html-for-dumbphones/8343>
 
Everything here is derived from those two. Any bugs in this version are mine, not theirs.
 
### Additional credits
 
- One of the source builds credits its Hebrew text to **the Metsudah Siddur via Sefaria**
  (CC-BY) and uses **Noto Serif Hebrew** (SIL Open Font License).
- One of the source builds carries the Yiddish credit line
  *אהערגעשטעלט דורך ׳שוואכע מעשיות - אייוועלט׳* and is dedicated
  *לע״נ מרן רבינו יואל ב״ר חנני׳ יום טוב זצוקללה״ה*. That dedication is preserved.
## What's included
 
Weekday Shacharis, Mincha, Maariv and Maariv for Motzei Shabbos; Sefiras HaOmer; Kiddush
Levana; Krias Shema al HaMitah; birchos hanehenin, bracha achrona and assorted brachos;
Tefillas HaDerech; Birkas HaMazon; Eruv Tavshilin; Netilas Lulav; Rosh Chodesh; Shalosh
Regalim; Nissan; the Haggadah; Shir HaShirim; Sukkos; Simchas Torah; Shavuos; Yotzros;
Chanukah; Purim; taaniyos and aveilus; seder hakrios; Birkas Kohanim; Tikkun Chatzos;
Tikkun HaKlali; and the full Tehillim.
 
## Features
 
- Fully vowelized text throughout
- **Hamburger sidebar** — every tefillah reachable from anywhere, grouped by category,
  with the current section highlighted. Slides in as a drawer on phones; on screens
  1100px and wider it stays open as a permanent sidebar.
- **Section jump menu** in the top bar of every service — a dropdown listing every
  sub-section (in Tehillim, all 150 perakim) that scrolls you straight to it
- Light / dark / auto theme (auto follows the device setting)
- Four text sizes and three line-spacing settings
- Five font choices (Times New Roman is the default; Vilna, SF Hebrew, and native
  sans/serif also embedded or referenced)
- **Responsive from dumbphone to big tablet** — text sizes step up automatically on
  larger screens, the home grid grows to 3–4 columns, and the reading column stays at
  a comfortable measure instead of stretching across a 13" display
- Works completely offline — save the file and open it
- Still **zero JavaScript**: every control (drawer, dropdowns, themes, sizes) is
  CSS-only, so it runs on browsers with scripts disabled or unavailable. The one
  tradeoff: settings can't persist across reloads without JS, so each open starts
  from the defaults.
## Usage
 
Save the `.html` file to the device and open it in the browser. That's the whole install.
It can also be hosted on any static web server or served from a local file path.
 
## Font licensing
 
This build deliberately keeps **Times New Roman** (Monotype) and **SF Hebrew** (Apple)
embedded as base64 data URIs, because Times New Roman is the intended reading face and
must render identically on devices that don't ship it. Be aware that neither vendor's
license permits redistributing font files, which is what base64-embedding amounts to —
that risk is accepted for this repo. If you fork this and want to be clean on licensing,
swap them for open alternatives:
 
- Noto Serif Hebrew (SIL OFL)
- Frank Ruehl CLM (GPL with font exception)
- Taamey D / Taamey Frank CLM (SIL OFL)
Doing so also cuts roughly 550 KB off the file size.
 
## Accessibility & printing

### Keyboard navigation

Hidden `<input class="state">` elements drive the CSS state machine and remain in the
browser tab order (they are not `display:none` or `visibility:hidden`). Pressing Tab
cycles through them; Space toggles the focused input. Round 4 adds `:focus-visible`
rings on the visible label that corresponds to each focused input — 60 selectors
covering all nav, theme, size, spacing, font, nusach, and checkbox inputs. The
hamburger button, gear button, jump-menu summary, jump-list links, and back-to-top
anchor also receive `:focus-visible` outlines.

### Colour contrast (WCAG AA)

All pairs tested in both light and dark themes pass WCAG AA:

| Element | Foreground | Background | Ratio | Level |
|---|---|---|---|---|
| Body text (light) | `#1d1a15` | `#f6f2e8` | 15.5:1 | AAA |
| Muted / rubric (light) | `#6f695e` | `#f6f2e8` | 4.87:1 | AA |
| Muted on card (light) | `#6f695e` | `#fffdf7` | 5.35:1 | AA |
| Category labels (light) | `#6b3a2a` | `#f6f2e8` | 8.30:1 | AAA |
| Body text (dark) | `#efece4` | `#111114` | 16.0:1 | AAA |
| Muted / rubric (dark) | `#9c968b` | `#111114` | 6.42:1 | AA |
| Muted on card (dark) | `#9c968b` | `#1b1b1f` | 5.84:1 | AA |
| Category labels (dark) | `#d09a7f` | `#111114` | 7.73:1 | AAA |

No palette changes were required.

### Printing

`@media print` hides all chrome (topbars, drawer, settings panel, intro screen,
jump menus, back-to-top buttons) and overrides colours to black on white. The CSS
state machine's `:checked` selectors apply normally in print mode, so the currently
active section appears and all others remain hidden — no JS needed. Page breaks are
advised before section headings via `break-after:avoid`. Print was verified by
reasoning from the CSS cascade; browser print-preview was not automated.

### ARIA

- `<nav class="side-list" aria-label="ניווט">` — the drawer navigation list.
- `<div class="settings-sheet" lang="en">` — the settings panel is labelled English.
- All 42 `.end-orn` decorative ornaments carry `aria-hidden="true"`.
- The drawer scrim and close labels already had `aria-label` from prior rounds.

## Text attribution
 
If the Hebrew text originates from Sefaria, the CC-BY license requires attribution in the
distributed file itself, not only in this README. Make sure the credit line stays in the
HTML.
 

