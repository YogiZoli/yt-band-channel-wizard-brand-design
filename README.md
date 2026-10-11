# Brand Channel Wizard, brand design version

A full duplicate of https://github.com/YogiZoli/yt-band-channel-wizard in the unified brand design ("Shine" v3), for a live side by side comparison.

- Original: https://yogizoli.github.io/yt-band-channel-wizard/
- Brand design: https://yogizoli.github.io/yt-band-channel-wizard-brand-design/

## What is the same

Everything functional: the three gates, the 13 questions, the email gate, `WEBHOOK_URL` and `PROGRAM_URL`, the kit texts and prompts, the paste back, the PDF and the .md export. The script block is the original, byte for byte, except the four lines listed below.

## What changed

- The whole `<style>` block: Shine tokens from `YogiZoli/design-system` (`tokens.css`), Open Sans and Geist Mono from Google Fonts, light theme only.
- PDF styling: the print styles, two inline text colours and the footer text colour.
- The `localStorage` key is `bcw_bd_state` (the original uses `bcw_state`). Both sites live on the same origin, so a shared key would make one version overwrite the other while comparing.

## Settings

At the top of the last `<script>` block in `index.html`: `WEBHOOK_URL` and `PROGRAM_URL`, same as the original.

## Reliability and logging

Same reliability pass and the same detailed event log as the original (v1.2.0). See the original README for the full list of events and the ways to read the log (footer links, `?debug=1`, console). The log lives under the `localStorage` key `bcw_bd_state_log`.

## Colour palette (v1.5.0)

Exactly this palette and no other colour, errors included. No red, no pink, no magenta, no purple.

| Role | Colour |
|---|---|
| Text | `#0F172A` |
| Muted text | `#475569` |
| Page background | `#F5F7FA` |
| Card surface | `#FFFFFF` |
| Borders | `#E2E8F0` |
| Teal, strong and tint | `#0E7490` and `#E6F4F7` |
| Navy, strong and tint | `#1E3A8A` and `#E8EDFB` |
| Emerald, strong and tint | `#047857` and `#E7F6F0` |
| Amber strong, tint | `#B45309` and `#FEF3E2` |
| Amber dark (errors and warnings) | `#92400E` on `#FEF3E2` |

- **Rotation**: content blocks take Teal, Navy, Emerald, then repeat. `paint()` sets `data-tone` (1 to 3) after each render. A block is its tint plus a 4px left border in the strong colour.
- **Teal strong with white text**: primary buttons, Copy buttons, progress bar, step numbers, links. Headings are the text colour with a Teal underline.
- **Updated**: `flag(el)` gives a block a short Amber glow, then a settled state with an Amber border, the Amber tint and a small "Updated" label. No animation under `prefers-reduced-motion`.
- **Errors and warnings**: Amber dark text on the Amber tint.
- **Result screen**: solid Teal with white text. **PDF**: Teal header and the same three tones.
- **Theme**: light only.
- **Back to the previous look**: the git tag `before-color-fix` marks the state before this change (the green version, v1.4.0): `git checkout before-color-fix -- index.html`.
