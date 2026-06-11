# Blue Inbox — Website

Landing page for Blue Inbox LLC, an AI data consulting service. The pitch: most of
what a company knows was never written down (it lives in meetings, spreadsheets, and
people's heads), so their AI tools give junk answers. Blue Inbox digs that knowledge
out, gets it in shape, and helps the client pick the AI tools that actually fit.
Advisory and tool-agnostic, not selling a platform.

Contact: david@blueinboxllc.com · LinkedIn: /in/david-zernik-los-angeles

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

Hero → big-picture quote band → "What this looks like" examples (Meetings, Tribal
knowledge, Scattered data, Tool choice) → "How I work" 3 steps → "What to expect"
principles → contact CTA → footer (email + LinkedIn).
