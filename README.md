# flipwits-site

The public site for Flip Wits, served by GitHub Pages at https://flipwits.hearthandwit.com. Plain HTML and one stylesheet, with no build step and no outside requests.

## The look

The site looks like the Flip Wits app, not like https://hearthandwit.com. A small "by Hearth & Wit" link in the top bar and the footer link keep the tie to the company.

- **Grounds.** The top bar, the home page hero and the footer are the game's near-black turn screen (#0B0B0F with white text). The rest of the page is the app's menu look: the grouped grey (#F2F2F7) with white surfaces, so the long support and privacy text is dark on light.
- **Mark.** The 42 app icon (a near-black rounded tile, a white rounded 42 and the green got-it bar), drawn as strokes so it needs no font. The same drawing is used on hearthandwit.com; `favicon.svg` is its tab-size cut.
- **Hero drawing.** The turn screen on a sideways phone, copied from the Flip Wits drawing on hearthandwit.com (its `.fw-*` rules). When the app's turn screen changes, redraw it in both places.
- **Type.** Nunito (the stand-in for the app's SF Pro Rounded on its design canvases) for headings, buttons and numbers, from `fonts/` (latin subset, weights 700, 800 and 900, with `fonts/OFL.txt`). Running text uses the system sans, as the app's menus use the system labels.
- **Shapes.** The app's radii: 16px for the small screens in the cards, 24px for cards and the text page surface, capsules for buttons, the testing note and the timer bars.

## Where the colors come from

Every color is a value from the iOS app's design tokens (`design/tokens.json` in `amceachin-code/math-phone-app`). If those change, change the custom properties at the top of `style.css` to match and recheck the contrast below.

| Token | Value | Used for | Contrast |
| --- | --- | --- | --- |
| Game ground / text | #0B0B0F / #FFFFFF | top bar, hero, footer, flash tiles | 19.64:1 |
| Soft text on ground | #D1D1D6 | hero paragraph, footer links, "by Hearth & Wit" | 12.91:1 |
| Grouped background | #F2F2F7 | page ground | headings #0B0B0F 17.60:1 |
| Surface | #FFFFFF | cards, text page | body #1C1C1E 17.01:1 |
| Muted text | #545458 | subtitle, date, lede | 6.75:1 on #F2F2F7, 7.54:1 on white |
| Accent violet | #6C4CF1 | links, Email button, focus ring on light | 5.33:1 on white, 4.77:1 on #F2F2F7; white on it 5.33:1 |
| Violet, deeper | #4A2FD0 | hover, skip link | white on it 8.05:1 |
| Violet, dark mode | #8B74FF | current page bar, hero arcs | 5.65:1 on #0B0B0F |
| Got it, light / dark | #009E73 / #1FB889 | up arrow on white / check and "Got it" on near-black | 3.42:1 (graphic) / 7.74:1 |
| Pass, light / dark | #D55E00 / #F07A1A | down arrow on white / pass glyph and "Pass" on near-black | 3.87:1 (graphic) / 7.02:1 |
| Warn, dark | #F2B134 | dot on the testing note | 9.00:1 on #1C1C1E (graphic) |

The light-mode green and orange only draw glyphs next to words, where 3:1 is the bar; as text they would fall short of 4.5:1 on white, so they are not used for text.

## Changing the site

When `style.css` or `favicon.svg` changes, bump the `?v=` tag on its links in all three pages, so browsers fetch the new file.
