---
name: create-graphic-novel
description: Create, adapt, direct, generate, revise, and package graphic novels or webtoons from source text, scripts, themes, images, fonts, or style references. Use for requests involving graphic-novel scripts, page plans, covers, storyboards, panel layouts, vertical-scroll episodes, character/style continuity, image-generation prompts, complete illustrated pages, dialogue or caption placement, page revisions, or production-ready handoff across projects.
---

# Create Graphic Novel

Produce a self-contained graphic-novel package that works without prior chat history. Preserve the source's meaning while converting prose into visual action, emotional beats, and readable page turns.

## Route the request

1. Identify the requested deliverable: script, storyboard, prompts, finished images, assembled pages, or a combination.
2. Choose a format:
   - **Paged:** cover plus fixed pages; use page turns and unequal panels.
   - **Vertical:** scrolling episode; use gutter length and vertical reveals.
   - **Single images:** one prompt or image per page/cut for later assembly.
3. Read `references/story-and-continuity.md` before adapting source material or defining recurring characters.
4. Read only the relevant direction guide:
   - paged work: `references/page-direction.md`
   - vertical work: `references/vertical-direction.md`
5. Read `references/prompt-and-production.md` when generating images, prompts, text overlays, or final files.
6. Read `references/quality-control.md` before delivery or when revising generated results.

## Establish the brief

Extract from the request and attachments:

`purpose | audience | language | format | page/cut count | aspect ratio | reading direction | source thesis | visual style | characters | text policy | output type | target tools`

Use explicit user choices as authoritative. If a noncritical choice is missing, apply these defaults and label them in the production brief:

- language: user's language
- format: paged graphic novel
- length: cover plus 8 story pages
- aspect-ratio options for generated paged/single-image work: **3:4 portrait** or **16:9 landscape**
- default ratio when the user does not choose: **3:4 portrait**
- reading order: left-to-right, top-to-bottom
- atmosphere: source-appropriate, avoiding unrequested grimness
- generated-frame text: none; composite captions and dialogue afterward
- script-overlay policy: **boxless first**; place text in negative space and avoid characters and focal objects
- prompts: English instructions with exact on-page copy preserved in its original language

Ask only if a missing choice would materially change the story, identity, doctrine, audience suitability, or deliverable. Do not re-ask for facts already present in attachments or conversation. If the requested output can reasonably be either portrait-page or widescreen, present the two supported generation choices as `3:4 portrait` and `16:9 landscape`; if the user does not choose, continue with 3:4.

## Lock page count and ratio before production

For paged graphic novels, treat the following as production locks unless the user explicitly overrides them in the current request:

- **Body length:** exactly 8 story pages by default.
- **Cover:** one separate cover; never count it as one of the 8 body pages.
- **Canvas option A:** **3:4 portrait** — default for conventional graphic-novel pages and covers.
- **Canvas option B:** **16:9 landscape** — supported for widescreen, presentation, video-frame, cinematic, or horizontal graphic-novel delivery.
- Never mix 3:4 and 16:9 within one deliverable unless the user explicitly requests mixed ratios.
- Record the selected specification at the top of the production brief, for example: `Cover 1 + Body 8 / 3:4 portrait` or `Cover 1 + Body 8 / 16:9 landscape`.

Run this check twice:

1. **Preflight:** before scripting, storyboarding, prompting, generating images, laying out text, revising, or exporting, confirm the body-page count and selected canvas ratio.
2. **Final gate:** before delivery, count the body pages again and inspect every page dimension. Correct missing, extra, cropped, stretched, mixed-ratio, or off-ratio pages before calling the work complete.

A reference image with another ratio does not override the selected production ratio. Explicit user instructions may change page count or ratio. When the user overrides either value, state the override clearly and use it consistently through production and final QA.

## Build a Project DNA block

Create this single source of truth before scripting:

- title, logline, thesis, audience, format, length, selected ratio
- visual medium, palette, linework, texture, lighting, mood
- character anchors: age range, face, hair, body, clothing, signature props
- environment anchors and recurring symbols
- typography: supplied font names, weights, hierarchy, safe margins
- text policy: clean art, composited text, or generated balloons; boxless-first overlay rule
- continuity locks: screen direction, costume, props, time, weather
- exclusions and likely model failure modes

Repeat character and style anchors verbatim in generation prompts. Treat style references as instructions for palette, texture, medium, composition, and mood—not as permission to copy their depicted subjects.

## Adapt story before designing pages

1. Extract the irreducible message and emotional arc.
2. Convert exposition into observable action, setting, gesture, symbol, or concise narration.
3. Divide the arc into beats; give every page or scroll segment one dramatic job.
4. Plant recurring visual motifs before their payoff.
5. Allocate quiet beats and transitions; do not fill every panel with explanation.
6. Preserve factual, philosophical, cultural, and doctrinal meaning. Flag any necessary interpretive choice.

For each page or segment, specify:

`beat | purpose | location/time | characters | action | emotion | motif | dialogue/narration | transition`

## Direct the visuals

- Choose panel count from the emotional beat, never from habit.
- Give the climax, reveal, or contemplative image the most visual area.
- Mix shot distances and angles with intent; maintain the 180-degree rule unless deliberately broken.
- Lock left/right placement, gaze direction, prop ownership, prop count, costume state, and light direction.
- Reserve negative space specifically for script placement.
- Treat every character's **face/head, torso/body silhouette, hands, and active gestures** as protected hard no-text zones.
- Treat **important props, symbols, tools, food, vehicles, reflections, environmental clues, and story-critical objects** as protected hard no-text zones.
- Expand protected zones with breathing margins so text neither overlaps nor visually crowds the subject.
- Keep each panel legible at final reading size.
- For a cover, prioritize one iconic image, title zone, silhouette, and tonal promise; do not summarize the entire plot.
- Adapt composition to the selected ratio: use vertical depth, stacked rhythm, and tall negative-space zones for 3:4; use lateral staging, horizontal eyelines, cinematic depth, and left/right text-safe zones for 16:9.

## Place script with minimal containers

**Text boxes are discouraged by default.** The preferred hierarchy is:

1. Place narration/dialogue directly in intentional negative space with no box.
2. Improve readability through font weight, line breaks, spacing, restrained outline/shadow, or subtle local contrast treatment.
3. If still necessary, use a compact balloon or caption shape fitted tightly and naturally to the copy.
4. Use a rectangular opaque/translucent text box only when the artwork provides no readable alternative and the box does not compete with the image.
5. If no safe placement exists, revise the composition or redistribute script across panels/pages; never cover protected characters or objects.

For all script placement:

- Follow reading order while prioritizing protected visual zones.
- Prefer quiet areas such as sky, walls, floors, water, mist, blank paper, soft-focus background, or intentionally reserved whitespace.
- Keep text away from face, head, torso, hands, gestures, and important objects even when a translucent background would technically keep them visible.
- Avoid long blocks. Break dense prose into concise units that support the visual rhythm.
- Recheck the whole page at final reading size after every text adjustment.

## Generate or assemble

When the user asks for actual images, use the available image-generation capability. Generate clean art by default, then add exact typography in a deterministic layout tool when feasible. If image generation must include text, keep it short and verify every glyph.

Create one prompt per page/cut rather than asking a model to invent the whole book at once. Each prompt must identify reference-image order explicitly and include:

`subject + action + environment + composition/panels + camera + lighting + medium/style tokens + palette + continuity anchors + selected ratio + reserved negative text space + protected visual zones + constraints`

Do not claim exact resolution or model-version support without verification. Preserve a user-specified model version; otherwise use a replaceable version token or omit it.

## Deliver in useful layers

Match scope to the request. A complete production package normally contains:

1. Project DNA
2. logline and beat map
3. character/style continuity sheet
4. cover plan
5. page/segment table
6. dialogue, narration, balloon type, and placement notes
7. copy-ready generation prompts
8. negative constraints
9. typography and assembly notes
10. quality-control report and revision list

If producing final files, keep editable clean art and composited pages separate. Use clear filenames such as `cover`, `page-01`, and `page-01-clean`. Never overwrite user attachments.

## Revise surgically

When the user asks to change one page, panel, person, hand, text box, ratio, or placement:

1. Inspect the current artifact.
2. State invariants: what must remain unchanged.
3. Edit only the requested region or page.
4. Recheck neighboring continuity and overall dimensions.
5. Re-run the page-count and selected-ratio gate; verify one separate cover plus exactly 8 body pages by default, and verify every generated page is consistently 3:4 or 16:9 according to the locked option.
6. Re-run the protected-zone gate: no script may overlap or crowd faces/heads, torsos, hands/gestures, or important objects; remove unnecessary text boxes wherever feasible.
7. Deliver the corrected artifact plus a concise change note.

Do not regenerate unrelated pages unless continuity makes it necessary or the user requests a full rebuild.
