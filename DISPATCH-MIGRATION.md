# Troop 450 — The Dispatch brand migration

This branch is an **isolated staging branch**, not a live TroopWebHost deployment.

## Source audit
- `core/master.css` uses broad global resets, hides native navbar controls, and forces blue/gold styles onto TWH tables and forms. Do not deploy unmodified.
- `core/master-logic.js` routes page IDs to Troop 774 assets at `stkrueger/t774-assets`, including missing pages. It also automatically redirects authenticated visitors. Do not activate for Troop 450.
- `pages/home.html`, `pages/prospect.html`, `pages/supplydepot.html` contain Troop 774 names, Florida location, fees, recruitment links, and third-party media URLs. They require content and routing conversion before publication.
- `pages/archivejscript.txt` embeds Troop 774 asset loaders; `cannon-board-ops.html` includes demo data and alert placeholders.
- Original media assets are preserved for review; confirm usage rights before republishing.

## Approved brand
Navy #15384E; slate #456377; olive #6D7656; paper #F5F0E6; cream #E9DDC7; red #AD4338.
Typography: Bitter (headlines), Source Serif 4 (body), Source Sans 3 (interface).

## Staging instructions
1. Use `core/dispatch-theme.css` after any existing styles, and wrap new public-facing content in `class="dispatch-theme"`.
2. Do **not** load the existing `core/master-logic.js` or `pages/archivejscript.txt` into Troop 450 until the router, page IDs and source paths have been corrected.
3. Replace all Troop 774 details and links with verified Troop 450 content.
4. Validate public pages, member navigation, keyboard accessibility, mobile layout, and native TWH forms before any rollout.
5. Keep this branch separate from `main` until reviewed.

This initial commit adds the brand foundation and audit only. It deliberately does not overwrite the original troop's pages.
