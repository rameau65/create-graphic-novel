# Prompt and production

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

## Negative constraints

Choose only relevant failures:

- character or costume drift
- duplicate or missing people/props
- extra limbs, malformed hands, fused anatomy
- mirrored screen direction or wrong eyeline
- copied subjects from the style reference
- panel bleed, missing borders, unreadable order
- unwanted text, watermark, signature
- flat default webtoon rendering when painterly texture is required

## Prompt template

```text
Create [page/cut and ratio] for a graphic novel.

REFERENCES: [ordinal role mapping]
STORY BEAT: [one dramatic job]
CONTINUITY: [verbatim character/style/state anchors]
COMPOSITION: [panel/cut plan, reading order, dominant image]
SCENE: [subject, action, environment]
CAMERA AND LIGHT: [shot, angle, lens feel, direction and quality]
STYLE: [token block plus subject-matter guard]
TEXT SPACE: [reserved zones or exact text policy]
CONSTRAINTS: [specific negative constraints]
```

## Assembly

- Keep source images at maximum practical quality.
- Apply one typography system across the book: title, narration, dialogue, SFX.
- Use the supplied font when licensed and available; provide a fallback otherwise.
- Define face bounding regions before placing text and expand them by a visual breathing margin. Treat these regions as hard exclusions for captions, balloons, tails, titles, and decorative text.
- Size each text container from its copy. Balance width, height, padding, line breaks, line length, and leading so the text fills the shape comfortably without looking cramped, stranded, or mechanically centered.
- Resolve overflow or imbalance by moving or reshaping the container before reducing type size. Preserve minimum readable type and revise wording only when authorized and semantically safe.
- Review all containers together at final reading size for consistent visual weight, clear reading order, and sufficient separation from faces and focal action.
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
