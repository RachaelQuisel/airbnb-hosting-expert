# Airbnb Hosting Expert video and website

The approved animation is published on [AirbnbAI’s My Work page](https://airbnbai.rent/automate.html#airbnb-hosting-expert).

## What the video shows

1. A listing starts with vague, unhelpful copy.
2. The host runs Airbnb Hosting Expert by name.
3. The plugin writes a clearer title and description.
4. Guests see the updated listing, smile, and click Book.

The host uses the finished text by copying and pasting it into Airbnb. The animation uses invented copy and drawn property scenes. It does not use La Maison’s real listing text or photographs.

The approved version retains the earlier 28-second composition. It includes the Airbnb logo in the website header and removes the typed writing prompt and added demo labels. It matches the painted scenery, cream paper, rounded navy lettering, and terracotta accents of the other AirbnbAI videos.

## Media files

- [Video](../assets/airbnb-hosting-expert-1920x1080.mp4): 28 seconds, 1920 × 1080, 30 fps, H.264, silent, 1,928,737 bytes.
- [Poster](../assets/airbnb-hosting-expert-video-poster.webp): 1920 × 1080 WebP.
- [Website card](../examples/website-card.html): the published card markup.

Video SHA-256: `cec07fd02a5739b056d0d27eb26dd2702117abea7c755958257cc05cd67d85f3`.

## Website publication

The card is the first item on My Work. It includes the video, a short explanation, a link to this repository, and a Learn more link. Learn more opens the existing contact form with Airbnb Hosting Expert selected.

The existing site pauses videos outside the viewport. Visitors who prefer reduced motion get manual playback controls.

The website update was pushed to the separate AirbnbAI site repository as commit `7d1bb0ac9c51d763c40f2aa9c93630c39dd58d03` and published through its Vercel integration. Vercel production deployment `dpl_5L469Ubbat145T2uKGpwWzx1Rrr3` was Ready and aliased to `airbnbai.rent`.

Verification confirmed that the live page, contact topic, video, and poster match the published files. The video plays on the production page and supports byte-range requests. All 11 existing website checks passed.

These repository additions document the video and website publication. The plugin package remains version 0.2.3.
