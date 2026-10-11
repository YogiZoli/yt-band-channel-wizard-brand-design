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

## Colour layer (v1.3.0)

From this version on, this repo is the one that is kept, and its script is no longer identical to the original: it carries a few visual hooks.

- **Tone rotation**: every top level block gets a tone in a fixed order, fuchsia, blue-green, coral, freesia: a tinted background and a 5px accent edge. `paint()` sets `data-tone` after each render.
- **Strongest accent** (fuchsia `#D91E50`): page title, question headings, step numbers, progress bar, primary buttons and Copy buttons. Smaller headings use `#B3163F` so they stay above 4.5:1 on the tints.
- **Updated highlight**: `flag(el)` gives a block a short glow, then a settled state with a fuchsia ring and an "Updated" label. It fires for kit blocks whose text changed since this browser last showed them, for a newly found research section, for an added image and for a file that is ready. No animation under `prefers-reduced-motion`.
- **Result screen**: solid fuchsia hero card with white text and coral and freesia light.
- **PDF**: fuchsia header, toned content blocks and tables in the same rotation.
- **Theme**: light only, there is no dark mode.
- The two tints without a token are the brand coral and freesia at low opacity (`--coral-tint`, `--freesia-tint`).
