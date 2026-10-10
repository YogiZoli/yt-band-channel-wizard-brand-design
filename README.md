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

## Reliability

Same reliability pass as the original (v1.1.0): status line, event log with "Copy a diagnostic report" in the footer, safe saved state, PDF and download fallbacks. See the original README for the list. The log lives under the `localStorage` key `bcw_bd_state_log`.
