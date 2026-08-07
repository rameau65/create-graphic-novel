# Webtoon & Graphic Novel project production policy

## Supported generation ratios

- **3:4 portrait**: default for paged graphic novels, covers, portrait story pages, and page-oriented illustration.
- **16:9 landscape**: option for cinematic, presentation, widescreen, and video-frame compositions.
- Lock the selected ratio before generation and keep it consistent across cover/body/cuts unless the user explicitly requests mixed ratios.
- Recompose or regenerate for ratio changes; never stretch finished art.

## Script and typography placement

1. Prefer no text box when direct script placement in negative space is readable.
2. Faces, heads, torsos/body silhouettes, hands, gestures, and important objects/props/symbols are hard no-text zones.
3. Add breathing margin around those zones; near-collisions also fail QA.
4. Use low-information negative space first: sky, wall, floor, water, shadow, soft-focus background.
5. If a caption/balloon is necessary, keep it minimal, copy-fitted, and visually balanced.
6. If safe space is insufficient, redistribute script or revise composition instead of covering characters or objects.

## QA gate

Reject wrong/mixed aspect ratios, stretched conversions, destructive crops, unnecessary rectangular text boxes, illegible typography, or any text that overlaps or crowds protected visual subjects.
