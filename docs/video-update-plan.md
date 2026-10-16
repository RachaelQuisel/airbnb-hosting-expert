# Airbnb Hosting Expert video update

## Current version and evidence

At the start of this review, the latest published video was `/assets/airbnb-hosting-expert-1920x1080.mp4`, introduced by website commit `7d1bb0ac9c51d763c40f2aa9c93630c39dd58d03`. On October 16, the live file still matched SHA-256 `cec07fd02a5739b056d0d27eb26dd2702117abea7c755958257cc05cd67d85f3`, 1,928,737 bytes, 28 seconds. The plugin repository contains the same file. Subsequent website commits concern staff SMS consent, not this video.

The existing renderer is `work/listing-video/render.mjs`. It draws one fixed background image on every frame. The original sky is baked into that image; petals and small clouds inside the property panels are the only related movement.

All seven reference videos were compared: scheduling cleaners, cleaning coverage, monthly tax reporting, guest door codes, inspections, booking sync, and Ops Today. Comparing the exposed top 125 pixels at 0.5 and 4.5 seconds gave an average pixel-channel difference of 14.15–14.37 in those videos, with 36–37% of sky pixels changing by more than 8/255. The Hosting Expert sky measured 0.003, with 0% changing by that amount. This establishes that its main clouds are static.

## Compare and contrast

| Area | Other seven videos | Current Hosting Expert video | Correction |
|---|---|---|---|
| Sky | Cloud shapes drift visibly across the painted sky | The whole sky is a fixed image | Separate clouds from the landscape and animate their positions |
| House | Cream stucco, terracotta roofs, organic edges, simple architectural detail | Heavy outlines, flat triangle roof, round blue door, distorted proportions | Paint a more convincing Spanish-style cottage in the established palette |
| Rooms | Soft edges and restrained illustrated detail | Hard outlined shapes and stretched furniture | Use consistent painted property art with aspect ratio preserved |
| Composition | Cream paper, navy lettering, terracotta step markers | Broadly consistent, but artwork reads as a different style | Keep the approved composition and improve the art within it |
| Motion review | Continuous scenery motion accompanies the workflow | Verification focused on playback and file delivery | Check background motion and visual quality in the encoded video |

## Initial plan and rubric

Initial plan: animate the clouds, replace the house illustrations, compare the result with the series, then re-export and replace the existing files.

| Criterion | Weight | Initial score | Revised-plan score |
|---|---:|---:|---:|
| Establish latest version; no duplicate card, repo, or new video filename | 15 | 13 | 15 |
| Continuous visible cloud motion and seamless looping | 25 | 17 | 25 |
| Painted artwork, architecture, palette, and proportions match the series | 25 | 18 | 23 |
| Preserve approved 28-second story, copy, plugin name, and Airbnb logo | 15 | 14 | 15 |
| Review encoded output, replace files in place, and verify publication | 20 | 12 | 20 |
| **Total** | **100** | **74** | **98** |

The initial plan lacked measurable motion requirements, a loop boundary check, and a visual review before export. The revised plan adds those requirements. Visual similarity retains two points of uncertainty until the artwork is rendered and compared.

## Final execution plan

1. **Locate the current files.** Reuse the existing website and plugin checkouts. Confirm clean working trees and preserve the newer unrelated website changes. Do not add another card, repository, or versioned public video URL.
2. **Rebuild the scenic layers.** Use the original series as the visual reference for a cloudless painted landscape and separate cream cloud artwork. Animate at least three clouds on continuous periodic paths, with differing movement and scales. Keep land and architecture fixed so the measured movement comes from clouds.
3. **Improve the property art.** Replace the flat cottage, living room, and hot-tub patio with consistent painted illustrations. Use plausible cottage proportions, an arched wooden door, cream stucco, terracotta tile, soft edges, and bougainvillea. Preserve image proportions when placing art into the existing panels.
4. **Preserve the approved narrative.** Keep the 28-second rough-copy → run Airbnb Hosting Expert → generated copy → guests smile and Book sequence. Keep invented copy, all-animation imagery, the plugin name, and the small Airbnb logo. Do not add a typed writing request or the removed labels.
5. **Review before and after encoding.** Compare representative scenes beside the seven references. Reject obvious stretching, heavy clip-art outlines, illegible text, or discontinuities before final export. Verify 1920 × 1080, 30 fps, 28 seconds, 840 frames, full decoding, and silent playback.
6. **Check cloud movement explicitly.** In the encoded output, target a mean sky difference of at least 5/255 and at least 10% of exposed sky pixels changing by more than 8/255 across four seconds. Confirm actual cloud positions move, not only texture or compression. Confirm analytic cloud positions match at 0 and 28 seconds, and inspect the end/start boundary.
7. **Replace in place and publish.** Replace the existing video and poster assets in the website and plugin repos, update the existing documentation and output links, run the website checks, push, and verify Vercel production. Verify live file hashes, playback, range requests, and exactly one Hosting Expert card.

## Export verification

Current output: 28 seconds, 1920 × 1080, 30 fps, 840 frames, H.264, silent, 3,312,715 bytes. SHA-256: `80036d6b6cd57ce574b6eeec0629867e466792698f76af34685b5f37d3463706`.

Decoded sky mean change: 9.39/255; sky pixels changing by more than 8/255: 26.44%. Fixed-landscape mean change: 0.016/255. Cloud displacement after four seconds: 179.8, 164.1, and 74.6 pixels. Cloud path end/start error: below 0.00000001 pixel. Full-frame encoded loop mean difference: 1.34/255, below the planned 1.5 threshold.

The original render's house proportions, heavy outlines, and static sky were rejected. The revised stills show an arched wooden door, painted tile and planting, and consistent room and patio artwork with the source aspect ratio preserved.

## Artwork provenance and prompt set

The built-in image-generation tool was used. The selected assets replace `work/listing-video/assets/background.png` and add the required animation layers `cloud.png` and `property-scenes.png`. These are working assets consumed by the existing renderer; the user-facing result remains the same existing video path in the plugin and website repositories.

Landscape prompt:

> Use case: precise-object-edit. Asset type: cloudless background plate for an existing 1920x1080 animated video series. Image 1 and Image 2 are references and Image 1 is the edit target. Remove ALL foreground paper panels, interior pictures, devices, text, UI, people and ALL CLOUDS. Reconstruct the painted landscape behind them in exactly this established soft gouache/cut-paper style and subdued palette. Keep the gradient sky pale creamy sage on the left and gentle pale blue on the right. Keep layered irregular sage-green hills and a charming cream stucco Santa Barbara Spanish cottage with terracotta tile roof at the far right lower half, with wooden arched door, little windows and rich magenta bougainvillea. The architecture should be graceful and plausibly proportioned, with hand-painted edges and warm light, not black-outlined clip art. The top half must be clear uninterrupted sky WITHOUT ANY CLOUDS because clouds will be animated as separate layers. Leave the central and left area quiet for the existing animated paper and screen. Wide 16:9, full bleed. Preserve the original series texture, colors, depth and level of detail. No words, panels, frames, UI, logos, people, cloud shapes, photographic elements, watermarks or heavy outlines.

Cloud prompt, with transparent-background output enabled:

> Use case: background-extraction. Asset type: a single transparent cloud sprite for the same hand-painted animation series. Reference image 1 shows the exact cloud style to match. Create ONE large broad fluffy cream cloud with gently irregular rounded lobes and a subtle pale grey-blue underside, made of soft matte gouache/cut-paper paint with delicate paper grain. Match the cream clouds in the reference, simple bold masses, softly feathered brush edges, NO outlines. Isolate only the cloud on a genuinely transparent background. Wide cloud silhouette around 2.4:1 aspect inside the image with transparent margin all around. No sky, landscape, ground, text, UI, sun, rain, face, shadow below the cloud or extra objects. This sprite will move across a separate painted sky.

Property artwork prompt:

> Use case: illustration-story. Asset type: one animation texture atlas with THREE wide landscape illustrations stacked VERTICALLY in three equal-height edge-to-edge rows, no gutters, dividers or labels. Each row is a complete wide scene. References 1 and 2 establish the exact warm soft gouache/cut-paper art direction, cream, terracotta, sage, muted blue, dusty pink, paper grain, organic brush edges, simple tasteful detail. No heavy outlines, no flat geometric clip art, no photorealism or 3D. TOP ROW: a beautiful small Santa Barbara Spanish-style cottage seen at a slight three-quarter angle, cream stucco, gracefully proportioned terracotta tiled roof, a normal human-sized ARCHED WOODEN DOOR, blue-green window trim, stepping-stone garden path, lavender and magenta bougainvillea. Make the cottage inviting and architecturally believable, not a toy and no circular door. MIDDLE ROW: its airy comfortable living room, muted sage sofa, oak coffee table, woven rug, cream curtains, soft sunlight, plants and garden window. BOTTOM ROW: its private garden patio, round wooden hot tub with a broad clear blue water ellipse in the LEFT half, pergola and outdoor dining table in the RIGHT half, terracotta pavers, lush restrained plants and bougainvillea. All three scenes must belong to the same illustrated home and exact same animation series as the references. Compose the important objects near each row's center so the images can crop to wide browser thumbnails. Absolutely no people, words, numbers, text, interface, border, watermark, logo or captions. Vertical three-row atlas; each of the three wide scene rows takes exactly one third of the overall image height.
