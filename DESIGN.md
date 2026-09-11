# INSPIRE — Design Notes

Single-file static site (`index.html`, Tailwind play CDN, no build step). Deployed on Vercel at www.inspirephysioclinic.com.

## Locked system
- Ground `#050505` (alt sections `#080808`, cards `#0a0a0a`), text `#F5F5F5`, muted `#B8B8B8`, signal green `#27C93F` (hover `#36B44A`).
- Type: Barlow Condensed 600-800 (display, uppercase H2s, two lines, second line green) + Space Grotesk (body, 10-11px uppercase tracked kickers).
- Section pattern: green kicker → two-line H2 → one short deck. Hairline grids (`gap-px` on a `white/6` ground).

## Image Art Direction
- Grade tier 2 (desaturate + slight contrast): `brightness(.8-.9) saturate(.85)` in CSS, `eq=saturation=0.88:contrast=1.04` baked into every encoded clip. Club crests are the exception: mono (`grayscale`) with per-crest `--lift`, full colour on hover.
- Owner footage is all vertical 9:16. Hero desktop = three 9:16 panels composed into one 1832x1080 file with 4px ink seams (`media/hero-triptych.mp4`); phones get a single vertical cut (`media/hero-mobile.mp4`). Both play at half speed (60fps source) so the reel's fast cuts read calm behind the H1.
- Section videos (`.lazy-video`) load and play only near the viewport, pause off-screen, and never load under reduced motion (poster only).
- Travel dispatches: portrait/landscape photos with an overlapping inset (6px ink mat), city name in display type sitting on a masthead fade into the photo, clip-path wipe on the main photo (trigger on the `<figure>`, never on a fully clipped `<img>`).
- On The Pitch ground: faint pitch markings SVG at 5% under the section.
- Motion: text uses the existing `.reveal` fade-up; travel photos wipe; crests lift on hover. `prefers-reduced-motion` shows final states.
- Sources: all footage and photos are the clinic's own (owner-supplied reels, July-Aug 2025 conference reels, May 2026 Ryze branch reel). Crests: club marks from Wikipedia, used to show where the team works.

## Content rules
- Only verified credentials. No invented roles (Pyramids FC has no role line until the owner gives one).
- Testimonials must be real Google reviews (current ones are placeholders, pending the owner's Google Business Profile link).
