# Airbnb Hosting Expert leaf-motion correction

**Overall Progress:** `100%`

## Goal and evidence

Correct only the ambient leaf/petal motion to fit the seven existing AirbnbAI videos. Preserve the accepted 28-second story, cottage artwork, listing copy, plugin name, Airbnb mark, 280 px/s clouds, particle colors/shapes/count, public filenames, and single My Work card.

Fresh production baseline: video SHA-256 `3ecd2911d6d96e36bc1d52278b5a1328d461b8e664f8fffb7388ce3e4ab71447`, 3,905,947 bytes; bytes match both existing checkouts. Website base `53088dca163dc0e700a9904dd0cb6c0a68bf3cea`; plugin base `22abb9b46d7661b39ee229e7ae9acb80d8c32fb7`.

The renderer moves petals horizontally at 22/29/36 px/s and vertically at a constant 33 px/s, wrapping y from about 1000 to 150 inside the picture. The reference clips show about 190–200 px/s lateral motion with vertical flutter. These are measurements from encoded videos; their original animation source is unavailable. The initial detector missed fast particles and confused static text edges with leaves; those estimates were rejected and retained separately, then tracking gates and moving-track filters were corrected.

## Rubric and revision

Initial draft: adjust petal paths, rerender the existing video, and publish it.

| Criterion | Weight | First draft | Revised plan | Revision |
| --- | ---: | ---: | ---: | --- |
| Evidence from all seven references and current production | 20 | 14 | 19 | Track colored moving components; reject stationary text; keep uncertainty explicit. |
| Motion fit: sideways drift, vertical flutter, tumbling | 25 | 15 | 24 | Target 192 px/s sideways, phased vertical oscillation, and roughly 1.1–1.2 rad/s tumbling; verify decoded output. |
| Preserve the accepted video | 15 | 15 | 15 | Restrict visual code diff to particle function; verify other source and assets unchanged. |
| Wrap and loop behavior | 15 | 7 | 14 | Remove vertical modulo; recycle horizontally offscreen; inspect frame-step continuity and existing end crossfade. |
| Export, GitHub, and live delivery | 15 | 11 | 15 | Full decode, byte identity, refreshed URL queries, production HTML, HTTP 206, and browser playback. |
| Mistakes, repairs, and post-run evidence | 10 | 6 | 10 | Complete audit and fix handoff, record actual failures and immutable commits, deliver report and preview. |
| **Total** | **100** | **68** | **97** | Plan score; not a claim of perfect visual quality. |

## Critical decisions

- Edit only `petal(t)` in the existing renderer. Keep its ten translucent pink ellipses and maximum dimensions. Use a steady 192 px/s breeze, smooth phase-offset vertical flutter, independent rotation phases, and offscreen horizontal recycling. Preserve the existing loop crossfade rather than add a new scene transition.
- Reuse the current repositories and public asset names. Do not duplicate cards, repositories, or public video files.
- Keep the pre-edit renderer/video as work-only baselines. Reject a render if any other visual source changes or cloud speed differs from the approved baseline.
- Renderer and analysis live in `work/listing-video/`. Plan and report are reviewable in `outputs/`; copy final plan/report/evidence into the existing plugin repository's `docs/`.
- Website changes are limited to the existing MP4, poster, and their version query strings in `automate.html`. Preserve all other site changes, including workshop links and newer staff-SMS work.
- Execution events use the installed execute skill's `scripts/log_event.py` with one run and attempt ID, from this task's root, writing `execute/.audit/events.jsonl`. A small work-only Python runner may manage the tracker and invoke that script.

## Tasks

- [x] 🟩 **1. Confirm the motion baseline**
  - Compare all seven reference clips, current production bytes, and renderer. Save measured tracks and immutable before artifacts. Verify the reference estimate with a coherent track, not stationary pixels.
- [x] 🟩 **2. Correct only the particle layer**
  - Replace the petal path and tumble calculations; preserve shapes, colors, count, clouds, art, copy, and timing. Render into the existing work draft and existing poster PNG.
- [x] 🟩 **3. Verify and visually compare the export**
  - Require a full 840-frame, 28-second, 1920×1080, 30fps silent decode. Track the encoded new petals near the reference lateral speed; confirm changing vertical direction; check no visible coordinate jumps and the end/start crossfade. Confirm only particle-function visual code changed, all source art is identical, and clouds still measure about 280 px/s. Inspect reference/new motion frames and a browser preview. Save a structured verification record.
- [x] 🟩 **4. Audit and fix substantiated mistakes**
  - Apply the Mistakes skill to this correction and relevant prior matching claims. Pass evidence to the bundled Fix Mistakes skill. Repair any actual in-scope defect, rerun affected checks, and preserve failed-run evidence. Do not invent faults or expand into unrelated site/plugin work.
- [x] 🟩 **5. Publish and verify the existing video**
  - Replace the existing site/plugin MP4 and posters only after checks pass. Refresh hash query strings. Update plugin `CHANGELOG.md`, `docs/video-showcase.md`, `docs/video-verification.json`, `examples/website-card.html`, and add the final plan, leaf verification, and post-run report under `docs/`. Run website tests, push both existing repos, and verify Vercel production, exact live bytes/URLs, one Hosting Expert card, range support, and actual playback. Record commits and a screenshot. If the report needs its final deployment identifiers, make one documentation-only follow-up commit.
- [x] 🟩 **6. Deliver the post-run report**
  - Reconcile every task with observed evidence, record original and revised rubric grades, list findings with their required fields and repair outcomes, include file sizes/hashes/commits, and deliver the current local video plus live page and report. Mark 100% only after publication and all required verification are complete.

## Planned artifacts

Existing: `work/listing-video/render.mjs`, `fully-animated-draft.mp4`, preview frames, `outputs/airbnb-hosting-expert-video-poster.png`, both repositories' existing Hosting Expert MP4/posters, website `automate.html`, plugin documentation listed above.

Work-only additions: `analyze-leaf-motion.mjs`, `verify-leaf-motion.mjs`, `leaf-run.py`, `leaf-run-state.json`, `leaf-motion-before.json`, `leaf-motion-after.json`, rejected initial detector evidence, before renderer/video, comparison frames/page, and publication results. These are verification/support files, not changes to the plugin package.

Reviewable additions: this plan, `outputs/airbnb-hosting-expert-leaf-motion-report.md`, a comparison image/live screenshot, plugin `docs/leaf-motion-plan.md`, `docs/leaf-motion-verification.json`, and `docs/leaf-motion-post-run.md`.
