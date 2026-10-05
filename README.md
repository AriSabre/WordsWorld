# WordsWorld

![WordsWorld](media/kiki-bouba-field.gif)

An emergent, first-person point-cloud environment. Typed words become space. Sharp (kiki) words pull teal points into solid planes that join at 90° or 45°; soft (bouba) words carve openings through them. Word length sets size and thickness. A pale stream threads every walkable opening.

Play it at https://arisabre.github.io/WordsWorld/ (or open `index.html` in a browser).

## Controls

- Click to look, WASD to walk, Enter to type a word or short phrase
- V switches walk / orbit view, G switches points / ghosted solids, H hides the HUD
- Backspace on an empty input erodes the last element; Shift+Backspace clears the field

## How it works

- **Two species of points.** Kiki points drift in stiff 45° steps; bouba points glide on a smooth chaotic flow (ABC flow). Both flock while travelling and keep spacing once they settle.
- **Hidden distance field.** Kiki words add boxes to a signed distance field; bouba words subtract extruded openings. Points never draw the field directly: they are recruited from the cloud and settle onto its surfaces.
- **Filters, not literal shapes.** Letter sounds give the kiki/bouba score, ascenders/descenders/x-height choose orientation, length sets size and thickness, syllables set repetition, typing speed sets how turbulently points settle.
- **Joins.** New planes hinge off existing ones at 90° or 45°; every third right-angle join turns to the third axis, so walls turn corners and roofs close over them.
- **Openings.** Bouba words always cut perpendicular through the nearest solid. Soft words grow organic openings; overlapping openings on one surface push deeper so they read as intersecting volumes.
- **Wayfinding.** An A* search over a walkability grid threads a stream of points through every opening you can walk through.
- **Nonsense.** Words not in the built-in English word list make the field flush red and sway.
