# Site build — August 25, 2026 (12 files changed)

Consolidates the openings system to a single `mode` key and fixes the live bug:
the site was in the full/waitlist state but the hero pointer on every page still
read "Now booking new clients." Pointer text is now derived from `mode`
automatically — a contradictory state is no longer possible.

Deploy the whole zip (it's the complete repo), or paste per-file in the GitHub
web editor. ⚠️ Web editor only — smart quotes from Word/Notes break the build.

## What changed

1. **_config.yml** — `show_public`, `waitlist_mode`, and `pointer` are gone.
   One key now controls everything:
   - `mode: "normal"`  → slot list; pointer "Now booking new clients…"
   - `mode: "hybrid"`  → slot list + waitlist path; pointer "Limited openings…"
   - `mode: "full"`    → waitlist state, no list, no phone; pointer "Currently
     full — join the waitlist"
   - `mode: "private"` → nothing public; walled /openings/ still works
   Safety net: an empty slots list forces the full state even if mode is stale.
   Currently set to `mode: "full"` (your live situation), as-of Aug 21 preserved,
   commented slot lines preserved for next time.

2. **_includes/openings_pointer.html** — pointer text derived from mode.
3. **_includes/openings_block.html** — three states keyed on mode; full state
   routes to the SimplePractice contact widget only (no phone).
4. **openings.html** — lede condition now reads mode instead of waitlist_mode.
5. **index, about, contact, couples-therapy, anxiety-trauma-emdr, adhd,
   adhd-in-women, stress-burnout, therapy-for-men** — visibility gate changed
   from `show_public` to `mode != "private"` (one line each).

## Your weekly edit now

Change `as_of`, edit `slots`, and set `mode` to match reality. That's it —
never touch pointer text. When full: `mode: "full"`, comment out the slots.
