# Airbnb Hosting Expert — leaf-motion post-run report

Date: October 24, 2026, America/Los_Angeles.

The website replacement is published and independently verified. The plugin repository media update and final tracker reconciliation are in progress; final GitHub records will be appended before delivery.

## Result and scope

The ambient petals now travel sideways at a 192 px/s source speed, with phase-offset vertical flutter and tumbling. Encoded tracking measures 193.83 px/s, compared with 188.64–199.16 px/s medians across the seven reference videos. The old video measured 23.27 px/s sideways and fell at a constant 33 px/s in source.

Only `petal(t)` changed in the visual renderer. Its ten translucent pink ellipses, colors, and dimensions are preserved. The cottage, listing copy, plugin invocation, Airbnb mark, all scene timings, 28-second duration, and 280 px/s clouds are unchanged. The existing filenames, repositories, and single Hosting Expert card are reused.

The plan was graded 68/100 initially and revised to 97/100 by adding measured reference motion, a particle-only source check, offscreen wrapping tests, decoded comparison, live delivery verification, and the audit/repair handoff. This is a plan grade, not a claim that the artwork is perfect.

## Mistakes

1. **I previously shipped mismatched petal motion and checked only part of the background animation.**
   - What I did: Left Hosting Expert's petals moving sideways at 22/29/36 px/s with constant 33 px/s downward movement. The y modulo recycled them from about 1000 to 150 within the frame. I then described the video as fitting the series after verifying the clouds, without separately checking the petals.
   - Why it was wrong: The other seven clips show much faster lateral wind and vertical flutter. A cloud-only comparison did not support a claim about all ambient motion.
   - Evidence: The saved pre-edit renderer's `petal(t)` contains the slow x speeds and `%850` vertical wrap. The production baseline hash is `3ecd2911d6d96e36bc1d52278b5a1328d461b8e664f8fffb7388ce3e4ab71447`. Encoded colored-component tracking measures a 23.27 px/s median sideways speed for that video, versus 188.64–199.16 px/s for the seven references. The user's visual comparison identified the remaining mismatch.
   - Impact: Hosting Expert's particles felt like slow falling confetti and could visibly jump vertically, making its movement inconsistent with the surrounding portfolio videos.
   - Correction: Changed only the petal function to 192 px/s sideways travel, phased vertical oscillation, and roughly 1.15 rad/s tumbling. Recycling happens beyond the left/right edges. The existing final crossfade remains in place. The encoded result measures 193.83 px/s, shows upward and downward motion, and passes the source, continuity, loop, and decode checks.
   - Prevention: Compare each ambient-motion layer against the reference series in the encoded export. Check trajectory, speed, rotation, recycling, and loop behavior before describing the whole animation as matching.
   - Repair outcome: Fixed and verified in the rendered artifact and on the production website. Exact live bytes and actual browser playback have been checked.

## Verification completed before publication

- Full decode: 840 frames, 28 seconds, 1920×1080, 30 fps, H.264, silent.
- Source diff: only the particle function changed; shapes, colors, and count are preserved.
- Encoded new particle motion: 193.83 px/s sideways, median tumble estimate 1.14 rad/s, vertical samples between −31.69 and +20 px/s in the tracked interval.
- Full-path continuity: no visible jumps across 840 source samples; 27 recycling events occurred beyond the screen edges. Both upward and downward movement are present.
- Clouds: 280 px/s in decoded output, correlation 0.9983.
- Non-particle scene comparisons: mean differences of 0.30–0.64 per 255 outside the particle masks, consistent with re-encoding. Visual source outside `petal(t)` is byte-identical.
- End/start comparison: mean 1.358 per 255, below the established 1.5 threshold.
- Browser preview: both the reference and new local videos play with readyState 4, no playback errors, and paused=false. Preview frames were inspected alongside the decoded measurements.

## Measurement quality and limits

The first analysis detector was unsuitable: it missed fast particles and included stationary text edges. Those results were rejected and saved as `work/listing-video/leaf-motion-initial-tracker-rejected.json`. The corrected detector rejects stationary candidates, follows coherent moving colored components, and is checked against explicit pixel tracks. No rejected zero-motion estimate was used to change the video or reported as the reference motion.

Reference motion is estimated from compressed video. The original renderers for those seven clips were unavailable, so this correction matches their measured pace and flutter rather than claiming identical source trajectories. The particle artwork was intentionally retained.

## Verified local artifact

- Video bytes: 4,177,781.
- Video SHA-256: `a95458706ea6ec4fce414cde515a7d3bc3525447344b2282afa6c189a8ee3697`.
- Renderer SHA-256: `c0a4375816f632d482f41d4fa211cee3a65bd7fa37e0f9e67379ddfe2e1b76ea`.
- Structured checks: `docs/leaf-motion-verification.json` in the plugin repository after publication.
- Run ID: `67cab6f0-4a32-4141-8743-b410c07524ce`.
- Attempt ID: `715a8b5b-ca0d-45ec-a055-e4d4a1fdee41`.
- Execution events: `execute/.audit/events.jsonl` in this task's workspace; recorded with the execute skill's logger.

## Production verification

- Website commit: `8f5a8ee2666d218fa47816f71a6cf864c31d91b9`.
- Vercel production deployment: `dpl_7KvwZkwKX7jrdE1MEr1TdMAJ6KV9`, Ready, aliased to `airbnbai.rent` and `www.airbnbai.rent`; confirmed with the existing authenticated CLI under the known team scope.
- The live page, homepage, video, and poster match their saved files byte-for-byte. The versioned MP4 also matches the canonical artifact and returns HTTP 206 for a range request.
- The single Hosting Expert card loads `airbnb-hosting-expert-1920x1080.mp4?v=a9545870` and poster query `v=32069b38`. No duplicate card or public video filename was added.
- Browser: duration 28, readyState 4, paused=false, 1920×1080, no error, current versioned source. A live screenshot was saved.
- Existing website tests: **21 passed, 0 failed, 0 skipped**. These were local tests, not a claim of a separate cloud CI run.
- The Vercel connector could not read this team scope (HTTP 403). This was a metadata-access constraint; no new account access was granted. The already authorized CLI confirmed Ready, and independent live HTTP and browser checks confirmed delivery. The failed connector check remains in the execution log.

No additional render or scope defect was found in the post-change audit. The rejected detector estimates and the connector-access failure are retained; neither is represented as a successful check.
