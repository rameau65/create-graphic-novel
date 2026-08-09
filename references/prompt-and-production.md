# Prompt and production

## Ratio lock

Every generated page/cut prompt must carry the production ratio selected in the brief.

- Supported standard options: **3:4 portrait** and **16:9 landscape**.
- Default for paged graphic novels: **3:4 portrait**.
- Use **16:9 landscape** when the user requests widescreen, cinematic, presentation, or video-frame composition.
- Keep cover and body on the same ratio unless explicitly overridden.
- Never stretch a finished image to convert ratios. Recompose, crop only when safe, or regenerate.
- For Midjourney-style prompt syntax, express the ratio through the appropriate aspect-ratio parameter when supported (for example `--ar 3:4` or `--ar 16:9`) rather than relying on prose alone.

## Reference order

Name every attached reference by ordinal and role:

1. character reference
2. style reference
3. previous page or continuity reference
4. location or prop reference

Tell the model to copy identity from character references, visual grammar from style references, and state from continuity references. Never say only “use the attached image.”

## Style token block

Extract and repeat:

`palette | medium | linework | color treatment | texture | lighting | mood | composition tendency`

Add a subject-matter guard: use only the reference's visual treatment; do not reproduce its people, buildings, scenery, symbols, text, or layout unless explicitly requested.

## Character anchor block

Repeat the same concise physical description, costume, scale, and signature props on every page. Specify exact prop count and occupied hand when duplication is likely.

## Clean-art default

Use:

> No letters, captions, speech balloons, sound-effect text, logos, signatures, or watermarks. Preserve intentional empty areas for later typography.

Composite exact dialogue and captions afterward when possible. If direct generation is required, enumerate all on-image text verbatim, define language, balloon type, speaker, and location, and prohibit extra text.

## Script overlay policy

Default to **boxless script placement**. Treat rectangular caption boxes, opaque text panels, and large speech containers as fallback devices rather than the normal solution.

1. Detect and mark protected visual regions before placing any script:
   - face, hair/head silhouette, neck, torso/body silhouette
   - hands, arms involved in gestures, and action paths
   - important props, symbols, tools, food, vehicles, reflections, signs, and story-critical environmental objects
2. Expand each protected region with a breathing margin. These expanded regions are hard exclusions for narration, dialogue, captions, titles, balloon bodies, and balloon tails.
3. Rank candidate text areas by visual quietness and reading order. Prefer negative space such as sky, walls, floor, water, blank paper, mist, soft-focus backgrounds, or intentionally reserved empty areas.
4. Place script directly on the artwork when contrast is sufficient. Improve legibility with typography, spacing, weight, restrained outline/shadow, or a subtle localized treatment before introducing a box.
5. If a text container is unavoidable, keep it compact, shape it to the available negative space, and minimize opacity and visual mass. Never use a large rectangle merely because it is easy to lay out.
6. If no safe text area exists, revise the composition or redistribute the script across panels/pages. Never cover a protected character or object to preserve the original text position.

## Negative constraints

Choose only relevant failures:

- character or costume drift
- duplicate or missing people/props
- exactly one head, two arms, two hands, two legs, and two feet per ordinary human figure; no extra, missing, duplicated, fused, detached, or malformed limbs, hands, feet, fingers, faces, torsos, or people
- mirrored screen direction or wrong eyeline
- copied subjects from the style reference
- panel bleed, missing borders, unreadable order
- unwanted text, watermark, signature
- flat default webtoon rendering when painterly texture is required
- wrong aspect ratio, mixed 3:4/16:9 canvases, stretched conversion, or unsafe crop
- text boxes dominating the artwork
- script overlapping or crowding faces, torsos, hands, gestures, important props, symbols, or focal objects
- text overlapping text; balloons, tails, titles, captions, dialogue, or SFX colliding with, clipping, or obscuring one another

## Prompt template

```text
Create [page/cut] for a graphic novel at the locked aspect ratio: [3:4 portrait OR 16:9 landscape].

REFERENCES: [ordinal role mapping]
STORY BEAT: [one dramatic job]
CONTINUITY: [verbatim character/style/state anchors]
COMPOSITION: [panel/cut plan, reading order, dominant image, ratio-aware staging]
SCENE: [subject, action, environment]
CAMERA AND LIGHT: [shot, angle, lens feel, direction and quality]
STYLE: [token block plus subject-matter guard]
TEXT SPACE: reserve visually quiet negative space away from faces, torsos, hands, gestures, important props and focal objects; prefer boxless script overlay in post-production
CONSTRAINTS: [specific negative constraints]
```

Every prompt containing people must state the anatomy constraint explicitly; do not rely on a generic “correct anatomy” phrase. Every prompt reserving text space must explicitly forbid text over focal elements and forbid all text-to-text collisions.

## Assembly

- Keep source images at maximum practical quality.
- Confirm every page matches the selected 3:4 or 16:9 canvas before typography.
- Apply one typography system across the book: title, narration, dialogue, SFX.
- Use the supplied font when licensed and available; provide a fallback otherwise.
- Define face, head, torso, hand/gesture, and important-object bounding regions before placing text; expand them by a visual breathing margin and treat them as hard exclusions.
- Search negative space first and place script directly without a text box whenever readability allows.
- Size any unavoidable text container from its copy. Balance width, height, padding, line breaks, line length, and leading so the text fills the shape comfortably without looking cramped, stranded, or mechanically centered.
- Resolve overflow or imbalance by moving text into safer negative space, reshaping a minimal container, redistributing script, or revising composition before reducing type size.
- Review all script placements together at final reading size for consistent visual weight, clear reading order, and sufficient separation from characters and focal objects.
- Inspect the composite at full resolution for text-to-text overlap, crossed balloon tails, clipped glyphs, and text crossing panel/page edges. Any collision requires reflow or relocation before export.
- Keep clean art, text overlay, and final composite as separate layers/files.
- Export a reading copy and retain editable masters.

## Print handoff

When the result will be printed, obtain the printer or platform specification before final export. Do not invent universal prepress values. Confirm:

`trim size | bleed | binding and inner margin | safe area | resolution | color profile | total ink limit | PDF standard | font embedding | overprint | proof method`

- Extend backgrounds through the required bleed while keeping faces, text, and essential symbols inside the safe area.
- Account for binding loss and left/right page parity.
- Use the printer's requested ICC profile and PDF preset; preserve an RGB master separately.
- Embed or outline fonts only as permitted by the font license, and keep an editable text master.
- Check Korean line breaks, punctuation hanging, forbidden line-start/line-end characters, ellipses, quotation marks, and minimum readable type size.
- Inspect a soft proof and, for consequential runs, request a physical proof before mass printing.
