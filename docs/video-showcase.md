# Airbnb Hosting Expert video and website

The approved animation is published on [AirbnbAI’s My Work page](https://airbnbai.rent/automate.html#airbnb-hosting-expert).

## What the video shows

1. A listing starts with vague, unhelpful copy.
2. The host runs Airbnb Hosting Expert by name.
3. The plugin writes a clearer title and description.
4. Guests see the updated listing, smile, and click Book.

The host uses the finished text by copying and pasting it into Airbnb. The animation uses invented copy and drawn property scenes. It does not use La Maison’s real listing text or photographs.

The current version retains the approved 28-second composition. It includes the Airbnb logo in the website header and removes the typed writing prompt and added demo labels. It matches the painted scenery, cream paper, rounded navy lettering, and terracotta accents of the other AirbnbAI videos.

## Media files

- [Video](../assets/airbnb-hosting-expert-1920x1080.mp4): 28 seconds, 1920 × 1080, 30 fps, H.264, silent, 4,177,781 bytes.
- [Poster](../assets/airbnb-hosting-expert-video-poster.webp): 1920 × 1080 WebP.
- [Website card](../examples/website-card.html): the published card markup.

Video SHA-256: `a95458706ea6ec4fce414cde515a7d3bc3525447344b2282afa6c189a8ee3697`.

## Website publication

The card is the first item on My Work. It includes the video, a short explanation, a link to this repository, and a Learn more link. Learn more opens the existing contact form with Airbnb Hosting Expert selected.

The existing site pauses videos outside the viewport. Visitors who prefer reduced motion get manual playback controls.

The original October 13 website update was pushed to the separate AirbnbAI site repository as commit `7d1bb0ac9c51d763c40f2aa9c93630c39dd58d03` and published through its Vercel integration. Vercel production deployment `dpl_5L469Ubbat145T2uKGpwWzx1Rrr3` was Ready and aliased to `airbnbai.rent`.

Verification confirmed that the live page, contact topic, video, and poster match the published files. The video plays on the production page and supports byte-range requests. All 11 existing website checks passed.

These repository additions document the video and website publication. The plugin package remains version 0.2.3.

## October 16 visual and motion update

The previous render used one static background plate, so its main clouds never moved. Its property illustrations also had heavy outlines and stretched proportions that differed from the other seven videos. Playback and delivery checks had passed without catching those visual problems.

This revision replaces the cottage, living room, patio, and landscape with cohesive painted art. Three separate transparent clouds move steadily across a fixed landscape. Property images preserve their proportions, and the end crossfades into the opening for the loop. The story, listing copy, plugin name, Airbnb logo, public video filename, and single website card are preserved.

The initial motion update was too slow: the encoded clouds moved at about 44 pixels per second. The cloud-only correction matches the other seven videos at 280 pixels per second (the references measure 276–280). Clouds travel in one direction and wrap continuously, completing four passes per 28-second loop. Decoded-frame comparisons confirm that the non-cloud scenes are preserved; only cloud-position code changed. The full 840-frame export decodes, and the end/start comparison passes the loop threshold. See [the verification record](video-verification.json).

The painted assets were generated with the built-in image-generation tool using the existing series as visual references. They were composited and animated in the renderer.

The artwork update was published from website commit `1833f3a2e1261617afb953fc51e9fad261b02562`. The cloud-only speed correction is published from website commit `e6eb0ca12423897788f1d984558de1f046a2943d`. Live video and poster bytes match this repository’s assets. The existing URL and single card are unchanged. The [comparison, graded plan, and artwork prompts](video-update-plan.md) record the review and acceptance criteria.

## October 24 particle-motion correction

The ambient petals now follow a 192 px/s sideways breeze with phased vertical flutter and tumbling. Decoded tracking measures 193.83 px/s, within the reference clips' 188.64–199.16 px/s median range. The former 22–36 px/s diagonal motion and visible vertical recycling are removed. Only the petal function changed; colors, shapes, count, clouds, house, copy, scenes, duration, and public filenames are preserved. Full decode, motion, loop, scope, and browser checks are recorded in [the leaf verification](leaf-motion-verification.json). The [graded plan](leaf-motion-plan.md) and [post-run report](leaf-motion-post-run.md) document the audit and delivery evidence.

The October 24 correction is published from website commit `8f5a8ee2666d218fa47816f71a6cf864c31d91b9`. Vercel production deployment `dpl_7KvwZkwKX7jrdE1MEr1TdMAJ6KV9` is Ready and aliased to airbnbai.rent. Exact live bytes, the versioned URL, HTTP 206, a single card, and browser playback were verified; all 21 current website tests passed.
