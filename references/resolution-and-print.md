# Resolution and print production

Use this specification whenever the deliverable includes generated pages, assembled page images, or PDF files.

## Why files become small or soft

A PDF does not create detail that is absent from its embedded page images. Common quality losses are:

- the image model returns a screen-sized native image;
- the page is assembled on a smaller canvas than the source;
- a preview, thumbnail, or screenshot is used instead of the master;
- the PDF exporter downsamples images or recompresses them as low-quality JPEG;
- a DPI metadata value is changed without adding pixels;
- the same JPEG is decoded and recompressed repeatedly;
- the physical PDF page is created at the wrong trim dimensions.

Treat pixel dimensions, physical page size, ppi, and file size as independent properties.

## Required master sizes

| Format | Minimum clean/composited master | Notes |
| --- | ---: | --- |
| 3:4 portrait | 3072 × 4096 px | 4K-class long edge |
| 16:9 landscape | 4096 × 2304 px | 4K-class long edge |
| Print | bleed-inclusive trim inches × 300 ppi | Use this when it is larger than the digital minimum |

Never stretch an image to change ratio. Crop, extend, or redesign the canvas explicitly.

If the generator cannot produce the target natively:

1. Generate at its highest native resolution in the locked ratio.
2. Keep the original lossless file.
3. Enlarge once with a high-quality super-resolution method.
4. Inspect faces, hands, linework, screentones, and lettering at 100%.
5. Add final typography only after the enlarged master is ready.

Do not describe a simple bicubic resize as newly generated 4K detail.

## Print calculation

Ask for the printer's trim, bleed, color, and PDF standard. When unavailable, use 300 ppi and provisional 3 mm bleed on every edge, and label these assumptions.

For each dimension:

```
bleed-inclusive inches = (trim millimetres + 2 × bleed millimetres) / 25.4
required pixels = ceil(bleed-inclusive inches × 300)
effective ppi = embedded image pixels / placed size in inches
```

The final page image must meet both the print calculation and the relevant 4K-class minimum. Use whichever requires more pixels.

Do not force A-series paper into 3:4 or 16:9. If ratios differ, obtain an explicit decision to crop, add margins/bleed extension, or change the production ratio.

## Assembly rules

- Build the page at final master dimensions from the start.
- Keep clean art, typography, and layout layers editable.
- Use supplied fonts and embed or outline them according to printer requirements.
- Keep text and line art sharp; avoid rasterizing early.
- Use PNG or TIFF for intermediate masters. Use JPEG only when required, at quality 95 or better.
- Avoid repeated JPEG saves.
- Never use chat previews or PDF page renders as production sources.

## Print PDF export

- Set the PDF MediaBox/TrimBox/BleedBox to the intended physical dimensions.
- Preserve images at 300 effective ppi or higher at placed size.
- Disable automatic downsampling below 300 ppi.
- Use lossless compression for line art when practical; otherwise use maximum-quality JPEG.
- Embed fonts.
- Use the printer-requested PDF/X preset and ICC profile. Do not guess a CMYK conversion when the printer has supplied no profile.
- Keep a separate print master and optional smaller screen/distribution PDF.
- Do not optimize or linearize the print master with settings that downsample its images.

## Acceptance checks

Reject and rebuild the output if any check fails:

1. Every master page meets the locked pixel dimensions.
2. Every page has the locked aspect ratio with no stretching.
3. Print pages match trim and bleed dimensions.
4. Effective image resolution is at least 300 ppi at placed size.
5. No page uses a thumbnail, screenshot, or preview render.
6. PDF export has not unintentionally downsampled or heavily recompressed images.
7. Fonts are embedded and text remains sharp at 200% zoom.
8. Fine linework, gradients, screentones, faces, and hands survive 100% inspection.
9. File-size reduction is explainable by efficient compression, not missing pixels.
10. A screen-optimized PDF, if produced, is clearly separate from the print master.

Record the dimensions and checks in the final quality-control report.
