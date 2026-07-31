# Site build — July 31, 2026 (4 files changed)

Replace each file's ENTIRE contents in the GitHub web editor with the version
in this folder. Commit all four together, then hit "Sync now" on the project's
GitHub connector so Claude's copy catches up.

## Files

1. **_config.yml** — adds `waitlist_mode: false` and `waitlist_url` to the
   `openings:` section, with comments documenting the three states. Your live
   values are preserved exactly: as-of July 27th, show_public: true, all four
   slots, and the two commented-out lines (Russ/Margaret + Wednesday).
   ⚠️ Paste in the GitHub web editor only — smart quotes from Word/Notes break
   the build.

2. **_includes/openings_block.html** — three-state rendering:
   - waitlist_mode false → today's behavior, unchanged.
   - waitlist_mode true + slots listed → slot list as normal, plus a
     "Don't see a time that fits? Join my waitlist" block under it
     (your current low-openings situation).
   - waitlist_mode true + slots empty (or all commented out) → full state:
     no list, prose disclosure (fees, private pay, in person), keep-looking
     permission, "Join the waitlist" button, phone fallback.
   The button points at the SimplePractice contact widget, not the scheduler.

3. **openings.html** — the page lede now adapts: in the full state it no
   longer promises "the list below shows the ongoing slots" (there is no
   list); it explains the waitlist instead. All other states unchanged.

4. **about.html** — Mindful Self-Compassion removed from Training & methods.
   Removal only; Somatic Experiencing stays off the site per the surface rule.

## How to run your current situation (few openings, not advertising)

Set `waitlist_mode: true` and keep editing as_of + slots weekly as usual.
The slot list keeps rendering, with the waitlist path underneath for anyone
the four times don't fit.

## When genuinely full

Comment out or delete every slot line (waitlist_mode stays true) — the page
converts to the full/waitlist state on the next build. Also set
`show_public: false` so the "Now booking" hero pointer doesn't advertise
openings you don't have.

## External-links sweep result

All external links site-wide already carried target="_blank" rel="noopener"
(booking buttons, Yelp/Google, LinkedIn, the About methods list). No other
files needed changes; the new waitlist buttons include it.

## Still your side (not in this build)

- Add the three waitlist questions to the SimplePractice contact-widget form
  (final wording from the July 30 session) BEFORE first flipping
  waitlist_mode on — the button targets that form.
- Verify which Yelp listing holds the 4.9 reviews (standing open item).
