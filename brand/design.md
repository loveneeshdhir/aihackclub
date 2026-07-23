# AI HackClub — Design System Spec (for AI / LLM use)

This file lets an AI assistant faithfully replicate the AI HackClub brand without seeing the source files. Follow it literally. All values are canonical.

## 1. Brand in one line
AI HackClub is a community of builders shipping with AI. Voice: direct, minimal, builder-to-builder. Aesthetic: flat, high-contrast, warm, squared-off. No gradients, no shadows (except overlays), no emoji.

## 2. Logotype
- Wordmark: `ai[hack]club` followed by an orange underscore block (the "cursor").
- Font: **Archivo, weight 800**, `letter-spacing:-0.02em`, lowercase, `line-height:1`.
- Square brackets are literal `[` `]` characters around `hack`.
- The underscore is a rectangular `<span>`, NOT a text character. Fixed ratio **2.6 : 1** (width:height). Color `#eb5b0c` on light/dark grounds; `#171310` when the ground itself is orange. It sits on the baseline: `display:inline-block; margin-left:~0.28em; margin-bottom:~0.12em`.
- Stacked lockup: two lines — `ai[hack]` / `club_` — centered, same weight.
- **`a[h]_` monogram** (compact mark for tight avatars, app icons, favicons): the wordmark abbreviated to `a[h]` + the same orange underscore block. Font: **Archivo, weight 900**, `letter-spacing:-0.02em`, `line-height:1`. Set the mark as a `display:flex; align-items:flex-end` row so the underscore sits on the baseline: `margin-left:~0.12em; margin-bottom:~0.13em` relative to font size. Same underscore ratio (**2.6 : 1**) and same color rules as the wordmark (`#eb5b0c` on light/dark grounds, `#171310` on orange). Center it in a 1:1 square; keep generous padding so it survives round crops.
- NEVER: recolor letters, stretch, rotate, add effects, change bracket spacing, or substitute the underscore with a typed `_`.

## 3. Color (canonical hex)
| Token | Hex | RGB | Role |
|---|---|---|---|
| --ink-900 | #171310 | 23,19,16 | brand black — ground + text |
| --ink-800 | #221d17 | 34,29,23 | raised dark surface |
| --ink-700 | #322b23 | 50,43,35 | dark border/divider |
| --cream-100 | #f5efe4 | 245,239,228 | brand cream — ground |
| --cream-200 | #ede4d3 | 237,228,211 | light hover |
| --cream-300 | #e0d4bd | 224,212,189 | light border |
| --paper | #fffdf8 | 255,253,248 | card white (warm) |
| --orange-500 | #eb5b0c | 235,91,12 | signal accent |
| --orange-600 | #cf4e07 | 207,78,7 | orange hover/press |
| --muted-on-light | #7d7466 | — | mono/meta text on cream |
| --muted-on-dark | #a89e8f | — | mono/meta text on black |
| body-text-on-cream | #3c352c | — | long-form body on cream |

**Rules:** black and cream are used in EQUAL measure — pick the one that contrasts context. Orange is a *signal*, never a field: use it for the underscore, ONE highlight, or ONE primary action per composition. Never a gradient. Status colors (sparing): ok #3d7a3d, warn #b3831a, error #c2340f.

## 4. Typography
- **Archivo** — display + body. Weights 400/500/700/800/900. Headings lowercase, `line-height:1.05`, `letter-spacing:-0.02em`. Body sentence case, `line-height:1.55`.
- **JetBrains Mono** — meta, labels, dates, tags, nav, numeric captions. Lowercase, `letter-spacing:0.06em`, often dot-separated (`berlin · 21 aug · 19:00`). Uppercase ONLY for short section labels with `letter-spacing:0.08–0.14em`.
- Scale (px): hero clamp(44,9vw,104)/900 · h1 44/800 · h2 32/700 · h3 22/700 · body-lg 18/400 · body 15/400 · mono 13.
- Fonts load: `https://fonts.googleapis.com/css2?family=Archivo:wght@400;500;600;700;800;900&family=JetBrains+Mono:wght@400;500;700&display=swap`.

## 5. Layout & surfaces
- Flat. Separate with **borders (1.5px, --cream-300 / --ink-700)**, not shadows. Shadows only for true overlays (`0 12px 40px rgba(23,19,16,.18)`).
- Radius: controls 8px, cards/frames 14px, small 4px, pill 999px (tags only). Brand is squared-off — keep radii modest.
- Spacing on a 4px grid: 4·8·12·16·24·32·48·64·96.
- Generous whitespace, strong left alignment, big type, one focal element per frame.
- Backgrounds are solid color fields — never photos/textures/patterns behind text. Imagery sits framed with a border, or as a faded duotone treatment.
- Section pattern: `border-top:2px solid #171310`, a mono index number (`01`) in orange beside a lowercase heading.

## 6. Motifs
1. **Underscore** — orange cursor ending a statement (`join us_`). Once per composition.
2. **Brackets** — square brackets highlight ONE key word (`open [build] hours`), typographic or as drawn 2px corner frames. Max once per layout.

## 7. Motion
Quick and dry: 120–200ms, `cubic-bezier(.2,0,0,1)`. Fades and small translates. No bounce, no scale-on-hover. Hover = darken (orange→#cf4e07) or subtle surface tint. Press = darken more, no shrink.

## 8. Copy
Lowercase headings, sentence-case body. Verbs first ("ship it", "bring a laptop"). "you"/"we". No hype, no title case, no emoji. Metadata in mono, dot-separated.

## 9. Iconography
No custom icon set. Prefer unicode micro-icons: `·` `[ ]` `_` `→` `×` `+`. If icons are required, use Lucide (2px stroke, `currentColor`, 16–20px). Never emoji, never hand-drawn SVG illustration as UI.

## 10. Replication checklist
Building anything on-brand? Verify: Archivo 800 lowercase headings · JetBrains Mono meta · exactly one orange accent · black OR cream ground · 1.5px borders not shadows · 8/14px radii · underscore present once · no gradients · no emoji.

## 11. Minimal HTML pattern (copy/paste starting point)
```html
<!-- wordmark with underscore -->
<div style="display:flex;align-items:flex-end;font-family:'Archivo',sans-serif;font-weight:800;font-size:44px;letter-spacing:-0.02em;color:#f5efe4;line-height:1">
  ai[hack]club<span style="display:inline-block;width:28px;height:11px;background:#eb5b0c;margin-left:12px;margin-bottom:6px"></span>
</div>
<!-- meta line -->
<div style="font-family:'JetBrains Mono',monospace;font-size:13px;letter-spacing:0.06em;color:#7d7466">bangalore · 1 aug · 12:00 pm</div>
```
