# SCS Version 8 — visual-editor ready package

**Status: prepared, not connected or deployed.** Original published Netlify review URL is unchanged.

This is an editor-enabled copy of the already-published Version 8 SCS review website.
It preserves the homepage, Skills/Innovation/Enterprise, Communities, Global Network,
full sitemap, upcoming programmes calendar, commercial services, video briefs and funder information.
All nine views remain in `index.html` and keep the same `#` navigation.

## What is prepared

- `index.html` — original website with CloudCannon `data-editable="source"` regions on selected headings, paragraphs and some CTA text.
- `cloudcannon.config.yml` — collection configuration to expose the index file for visual editing.
- `.cloudcannon/initial-site-settings.json` — suggested static-site build defaults.
- `netlify.toml` — Netlify publish root; no build command needed.
- `robots.txt` and `_headers` — preserve draft no-index signals (not authentication).
- `SCS_editable_region_inventory.csv` — inventory for a technical administrator.

**Important:** CloudCannon visual editing has **not** been tested against a real CloudCannon account.
Its build settings, preview routing, and ability to edit all nine hash-route views must
be checked in CloudCannon before relying on this for team editing. CloudCannon and
Netlify need to be connected to the same GitHub repository for automated publishing.

## Setup steps — editor can change wording without HTML

1. Keep your existing Netlify website online. Do not replace it until editing has been verified.
2. Create or choose a private GitHub repository (for example, `scs-team-review`). Upload the contents of this unzipped folder to the **repository root**, with `index.html` at the top level.
3. In Netlify, open the existing SCS project and go to **Project configuration → Developer settings → Continuous deployment → Repository → Link repository**. Connect the same GitHub repository. Netlify will serve the static files directly from the root. This preserves the existing Netlify URL if you connect the existing site rather than creating another.
4. At https://app.cloudcannon.com/ start a CloudCannon trial and create a Site from the **same** GitHub repository. Select static site. Confirm it builds with `output_path` `.` and no install/build command. The source repository is the single source of truth.
5. Open the `SCS Website Copy` collection, select `index.html`, and test the Visual Editor. Click a highlighted heading or paragraph to edit. Navigate to the other pages via the preview's links, testing one page at a time; the entire site currently uses in-page hash routing.
6. Invite only the designated SCS wording editor as an Editor. Keep administration and layout/code access limited to one administrator. CloudCannon role/permission availability depends on the plan.
7. Make one harmless test edit (e.g. add a punctuation mark), **save** the change, verify the commit in GitHub and update in Netlify. Then revert test punctuation. Confirm links and responsive layout work.
8. For important copy, use an SCS approval rule before changing the live review website. Avoid changing dates, financial claims, programme status and legal claims without a content check.

## Publishing and safety

- CloudCannon, Netlify and GitHub are **not connected** by this package alone; each requires signing in and authorization.
- Changes made in CloudCannon can sync to GitHub and automatically deploy in Netlify after you connect all three services.
- Only copy is designated as editable. Link destinations, HTML structure, styles, JavaScript and visual assets are not exposed as editing regions.
- Do not give the editor Netlify Owner credentials or GitHub admin credentials; use appropriate permissions.
- Netlify preview URL can be public even when the GitHub repository and editor login are private.
- CloudCannon pricing can change. Check current trial and subscription details before committing.
- The layout/navigation remains Version 8. Do not use this as a license to rewrite the approved storyline.

## Helpful reference URLs

CloudCannon: https://app.cloudcannon.com/
CloudCannon editable regions: https://cloudcannon.com/documentation/developer-reference/editable-regions/
CloudCannon and Netlify: https://cloudcannon.com/documentation/developer-articles/netlify-hosting-with-cloudcannon-editing/
Netlify linking: https://docs.netlify.com/build/git-workflows/repo-permissions-linking/
