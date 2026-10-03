---
name: urlbox-web-capture
description: Use when the user asks to screenshot a web page, save it as a PDF, record it as a video, or get its content as Markdown, text or rendered HTML with Urlbox. Explains which Urlbox tool fits each request and which render options matter.
---

# Capturing web pages with Urlbox

Urlbox renders a page in a real browser, so it captures what a visitor sees,
including content that only appears after JavaScript runs.

## Pick the tool by what the user wants back

| The user wants | Tool |
|---|---|
| An image of the page | `screenshot` |
| A PDF of the page | `pdf` |
| A video of the page scrolling | `record_video` |
| The page's readable content | `markdown` (structure kept) or `extract_text` (plain text) |
| The HTML after scripts ran | `scrape_html` |
| Several formats from one render, or an option the others don't expose | `render` |

Use `describe_options` to look up any render option by name before using it.
Common options are fields on each tool; any other option goes in the tool's
`options` object.

## Options worth knowing

- **Whole page, not just the first screen:** `full_page: true`.
- **Cookie banners and popups:** `hide_cookie_banners: true`, `click_accept: true`.
- **Ads:** `block_ads: true`.
- **Sharp images:** `retina: true`.
- **Viewport:** `width` and `height` in pixels; a phone is around 390 by 844.
- **Dark mode:** `dark_mode: true`.
- **One element only:** `selector` with a CSS selector.
- **Pages that load slowly:** `delay` in milliseconds, or `wait_for` a CSS
  selector that appears when the page is ready.

## Projects, usage and problems

- Renders go to the default project chosen at sign-in. `list_projects`
  shows others; pass `project` to use one.
- `usage` shows how many renders the plan has left.
- If a render does not match the live page, `report_render` sends it to the
  Urlbox team with a short description of what is wrong.
