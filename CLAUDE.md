# Blue Inbox Website

Landing page for Blue Inbox LLC, a web development business offering business websites,
online stores and custom web tools. The site connects to the fictional Blue Inbox
series on SwayFrame, with an explicit distinction between the show and real services.

Public copy uses the company voice. No personal names, personal biography or personal
LinkedIn links. Existing contact email remains the destination behind company-labeled
contact links. Do not invent client results, testimonials, credentials or prices.

## Tech

- Single static `index.html`. No build step, no dependencies, no framework.
- Inline `<style>` in the `<head>`. Plain HTML/CSS only.
- To preview: open `index.html` in a browser.

## Deployment

- Hosted on **GitHub Pages** from this repo (`blueinbox-admin/blueinboxwebsite`),
  branch `master`, folder root `/`.
- Live at **blueinboxllc.com** (apex is canonical; `www` redirects to it).
- **To ship a change:** edit `index.html`, commit, `git push origin master`.
  Pages redeploys automatically in ~1 minute.
- DNS is managed via the Hostinger API. The domain's email is Google Workspace —
  never modify the MX / SPF / DKIM / DMARC records or email breaks.

## Copy voice (important)

Write like Sam Parr recommends:
- Short sentences. One idea each.
- Plain, simple words. No jargon ("dig it out," not "extract and operationalize").
- Conversational. Lead with the reader's pain, not our service.
- Concrete examples over abstract claims.
- Not salesy. Advisory tone. "No sales pitch" energy.

**Hard rule: never use em-dashes (—) or en-dashes (–) anywhere.** Use periods,
commas, or restructure the sentence instead.

## Design system

Warm, editorial, understated (inspired by zoutcomes.com). Reads "trusted advisor,"
not "tech vendor."

- **Font:** Georgia serif throughout. Headings are normal weight (400), not bold.
  Italics in the accent green for emphasis.
- **Palette (CSS vars at top of `index.html`):**
  - Background cream `#f5f1e8`, soft cream `#efe9dc`, paper `#faf7f0`
  - Ink `#1a1a1a` / `#3a3a2d`, muted `#6e6a55`, faint `#a89878`
  - Accent green `#395a56`, deep green `#2f3a32` (footer bg)
  - Hairline rules `#ddd5c4`
- Lots of whitespace. Thin `1px` rules between sections. Uppercase letter-spaced
  eyebrow labels. No gradients, no glow, no emoji in body copy.

## Structure of index.html

Hero and SwayFrame feature link, services, three-step process, Blue Inbox series
feature, contact CTA, footer. The old personal consulting pitch and gated setup
video have been removed. No JavaScript or client-side password gate is needed.

## Note

The Active Memory / Zoutcomes product (the app Blue Inbox installs) lives in a
separate repo: `~/Desktop/projects/memoryapp`. This repo is only the marketing
website.
