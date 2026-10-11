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

## Colour layer (v1.4.0): green

Green is the base colour of the Brand Channel Wizard. Everything is green or blue-green. Red appears only when something failed.

This repo is the one that is kept. Its script is no longer identical to the original: it carries a few visual hooks.

- **Greens** come from the design system's green scale (`tokens.v1.css`, `accent-*`): `#E4F5EA`, `#BFE8CC`, `#24A957`, `#0E8542`, `#0C6A36`, `#0C5430`. **Blue-greens** come from the Shine live scale: `#E3F7F6`, `#C4EEEC`, `#00B1B0`, `#00807F`, `#006564`.
- **Tone rotation**: every top level block gets a tone in a fixed order, green, blue-green, mint, aqua: a background that runs from one shade into a lighter one, and a 5px accent edge. `paint()` sets `data-tone` after each render.
- **Actions**: buttons, Copy buttons, step numbers and the "Updated" label run from `#0E8542` into `#0C6A36`. The progress bar and the top line run from green into blue-green.
- **Updated highlight**: `flag(el)` gives a block a short green glow, then a settled state with a green ring and an "Updated" label. No animation under `prefers-reduced-motion`.
- **Result screen**: deep green hero card (`#0E8542` into `#0C5430`) with white text.
- **PDF**: green header and toned blocks in the same rotation.
- **Errors**: the warm orange-red danger tokens, used only for error messages.
- **Theme**: light only, there is no dark mode.
