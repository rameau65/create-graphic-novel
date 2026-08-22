# Project skill/MD sync index

Source packages synchronized from the Webtoon & Graphic Novel project. Visual-generation skills use the shared 3:4 / 16:9 and text-safe production policy.

## Packages

- `Portable_Meditation_Video_Framework_v1.0.skill`: SKILL, project brief, standalone prompt, adapters, example, QC
- `aitoon-page-director.skill`: README, SKILL, design brief, title prompt, direction rules, prompt templates, style tokens, balloon/SFX dictionaries, QC/fixes, examples
- `aitoon-vertical-director.skill`: README, SKILL, vertical direction rules, cut prompt templates, gutter guide, style tokens, balloon dictionary, gotchas
- `aitoon.skill`: SKILL, Midjourney prompt rules, stage1, stage1-2, stage2, stage_insta
- `frontend-design-by-blue.skill`: SKILL
- `style-page-by-blue.skill`: SKILL, framing guide, gotchas, prompt template, style analysis
- `stylish-infographic-by-blue.skill`: SKILL, design brief, examples, feedback diagnosis, four-block framework, style extraction
- `token-optimizer.skill`: SKILL, design brief, gotchas, phase 1/2/3 rules
- `novel-writer-v0.4.3.plugin`: README, agents, novel-writer SKILL, harness
- `script-adaptor-v0.7.5.plugin`: screenplay/stageplay/comicscript/adaptor SKILLs, scene/stage/comic agents, visual director, character actor, rules

## Extracted Markdown count

79 Markdown documents including the shared production policy and this index were extracted and validated locally from the project packages. Visual-production entrypoints were patched with the shared policy; non-visual writing/optimization skills remain source-faithful.

## Shared visual policy

- Ratios: `3:4 portrait` or `16:9 landscape`; 3:4 remains the default for paged graphic novels.
- Minimize rectangular text boxes.
- Prefer direct script placement in intentional negative space.
- Faces, heads, torsos/body silhouettes, hands, gestures, and important objects/props/symbols are hard no-text zones with breathing margin.
- If safe space is insufficient, redistribute copy or revise composition rather than cover the subject.

## Shared delivery policy

- Default final-delivery destination: [Google Drive `graphic novel` folder](https://drive.google.com/drive/folders/1NZDZ_PIb_tcvbTliI5yof8dQ4g4-7puv).
- Upload all user-facing final files and requested editable masters; omit disposable intermediates.
- Verify uploaded file IDs or links before reporting completion.
- A newer task-specific destination from the user takes precedence.
