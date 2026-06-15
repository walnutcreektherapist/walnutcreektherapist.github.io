# Walnut Creek Therapists — Jekyll site

Static Jekyll site for GitHub Pages. Editorial Calm design (Spectral + Hanken Grotesk;
warm oat / sage / forest / brass). Brand: **Measured therapy. Real skills. Honest answers.**

## Staging with a redesign branch (so the live site is never at risk)
1. In your repo, create a branch off main:  `git checkout -b redesign`
2. Drop these files in, commit, and push:  `git add -A && git commit -m "New site" && git push -u origin redesign`
3. Preview it without touching the live site, either:
   - locally: `bundle install && bundle exec jekyll serve` → http://localhost:4000, or
   - on GitHub: temporarily set Settings → Pages → Source to the `redesign` branch to view it live, then switch back.
4. When you're happy, go live by merging:  `git checkout main && git merge redesign && git push`
   (or just set Pages → Source to `redesign` permanently). The live domain only changes at this step.

GitHub Pages builds Jekyll automatically — no local Ruby required to publish.
`jekyll-sitemap` generates /sitemap.xml. The `CNAME` file points the site at walnutcreektherapists.com.

## Pages
`/` · `/couples-therapy/` · `/anxiety-trauma-emdr/` · `/adhd/` · `/about/` · `/contact/`
Nav, footer, contact card, FAQ, reviews, welcome, and all SEO/schema live in `_includes` / `_layouts` — edit once.

## Add your assets
- Keep your existing **favicon**: drop `favicon.ico` in the repo root (already linked in the head).
- Nature photo → `assets/img/nature.jpg` (home banner; falls back to a sage band if absent).
- Headshot → `assets/img/matthew-rojo.jpg`, then swap the `.portrait` monogram block in `about.html` for the commented `<img>` line.
- Official **Yelp badge**: paste the embed from biz.yelp.com into the marked slot in `_includes/reviews.html`.

## Confirm in _config.yml before launch
- **license**: MFC46949 (your live site shows this) — verify on the CA BBS lookup.
- **phone**: (925) 315-8205 everywhere; retire the 415 number if dead.
- **same_as**: add your exact Psychology Today and Facebook URLs.
- **reviews.yelp_url / google_url / blurb**: confirm which Yelp listing holds your reviews and your current rating.
- **legal_name**: leave blank now. After the court approves your name change, set it to "Matthew Lindgren" and a discreet CAMFT disclosure line appears in the footer.
- **fees**: $275 individual / $305 couples — confirm.

## Coming next
- Therapy for men, Betrayal & affair recovery, Ketamine-assisted psychotherapy (new `.html` file + one line in `nav`).
- Online couples classes — likely a separate brand/listing for clean review solicitation.
