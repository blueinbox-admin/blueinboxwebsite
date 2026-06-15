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

## Active Memory (the product Blue Inbox installs) — how it works

A companion app ("Active Memory," Zoutcomes-style) that holds the company brain and
feeds it to Claude Code via MCP. Prototype: `~/Desktop/memory-app-mockup2.html`
(live at blueinbox-admin.github.io/ideas/activememory2/).

The bet, in plain terms:

- **Answers become structured records, not loose text.** Each question the owner answers
  saves as a small record: an *area* (e.g. "client matching"), the *rule* itself ("match by
  email first, then full name"), and *tags* for the systems and task it applies to
  (`quickbooks`, `wordpress`). The question card is just the friendly front end for writing
  that record.
- **Read-only toward outside apps.** The app holds read-scoped credentials to read and map
  data across the owner's tools (HubSpot, QuickBooks, WordPress). It never writes to them. It
  reads, maps entities (this HubSpot company = that QuickBooks customer), and remembers. A leak
  is a privacy problem, not a catastrophe. "We only ever hold read access" is a selling point.
- **Claude Code does the writing**, with the human confirming. The app is the brain, Claude is
  the hands. Don't build the universal writer (that's an integration platform with a lawsuit attached).
- **One MCP server.** The app runs an MCP server Claude Code connects to once. It exposes tools
  like `search_memory(task)` / `get_rules(topic)`.
- **"At the right time" = retrieval.** When the owner tells Claude Code to do a task ("match this
  week's payments to client records"), Claude queries the MCP, the server returns the
  sharply-tagged rule(s) for that task, and Claude applies them before acting. The rule is not a
  prompt you paste, it's a fact Claude looks up itself when the task is relevant.
- **The real job (what's hard to copy):** (1) tag each rule to the systems + task so retrieval is
  sharp and Claude gets the one rule that matters, and (2) write MCP tool descriptions that tell
  Claude to check memory before these tasks. Anyone can store text; the value is in tagging + retrieval.
- **Positioning:** the brain is the asset and the moat, and it's tool-agnostic. The model is
  `You <-> the map (brain) <-> Claude Code`, with the brain its own box in the middle. Do NOT fold
  the memory "into Claude" (that makes us a Claude feature with no answer to "why not just use
  Claude's own memory?"). Keep it separate so any AI can read it.
