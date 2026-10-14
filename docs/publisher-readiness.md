# Airbnb Hosting Expert publisher preparation

Prepared October 12, 2026, for the existing private OpenAI/Codex plugin. Public submission remains incomplete. This document reports source and package checks, not approval by a directory.

Version 0.2.3 was saved to [the existing plugin](https://chatgpt.com/plugins/plugin_c92d5838e8888191a91d00efe93ef5cd) as private release pluginrel_6acd4ea758c88191b4817175acf2dc0a. Source readback and a downloaded copy of that saved release match the exported text and new icon bytes. The previous icon is absent from the current saved file inventory and archive. The current icon includes the official Airbnb mark at the publisher's request; the publisher confirmed written permission in this chat. The downloadable ZIP includes the backend-synchronized Codex compatibility metadata.

## Current icon update in version 0.2.3

The publisher requested Ghibli Icon Maker and confirmed written permission to use the Airbnb logo. The replacement uses the skill's original renderer helpers and Sheet API, unchanged. The main drawing is a warm charcoal outline of a guesthouse and message bubble on a washed oat squircle. The secondary Airbnb mark uses exact SVG geometry and the Rausch color from [Airbnb's homepage](https://www.airbnb.com/). No sparkle is included. Logo permission is publisher-reported; no separate permission document was inspected.

The full-size icon and 128-pixel and 48-pixel thumbnails were visually reviewed on light and dark backgrounds. Lossless recompression verified identical decoded pixels. The saved release's icon bytes match the delivered PNG.

## Hosting-instruction changes retained from version 0.2.2

- Replace generic migrated GPT instructions with listing, guest-message, review-response, and hosting-improvement workflows.
- Remove the property address, access code, shortened guidebook link, guest-specific dates, and publisher signature from reusable examples.
- Require confirmed facts before saying a reservation change, repair, or refund is complete. A draft does not send a message or change a reservation.
- Add official-source verification for current policy questions, limits on account access, and guidance for handling guest data.
- Keep a warm, concise hosting voice and the existing three starter prompts.
- Use a 29-character subtitle and synchronize the root and Codex compatibility manifests.
- Add an independence disclosure. The current icon is the Soft Index guesthouse and message illustration with the Airbnb logo authorized by the publisher.
- Add README, package data-handling disclosure, release notes, and focused reference guides.

## Checks completed

- Root manifest validates against the Agent Plugins 1.0.0 JSON schema retrieved for this preparation.
- Skill component validation passes with Claude Code 2.1.288. This checks skill structure; it does not make this an installable Claude marketplace package.
- Name, author metadata, default-prompt type, prompt text, and prompt order are preserved.
- Display name: 21 characters. Subtitle: 29 characters. Detailed description: 775 characters. Developer-name text: 14 characters.
- The manifests agree on identity, version, descriptions, icons, and starter prompts.
- Skill references resolve. The supplied property-specific examples are absent from the candidate source.
- Icon is a square 1024 by 1024 RGBA PNG, 760,981 bytes (743.1 KiB), with transparent corners and softly feathered squircle edges. It is below OpenAI's 5 MiB limit and the skill's approximate 750 KiB target. The main drawing uses warm charcoal (62, 52, 46) and stroke width 0.0248. Final archive checks verify the icon bytes are included.
- The package contains no MCP configuration, App binding, executable script, hook, or symlink. No MCP cases, demo recording, or reviewer account are required for this skills-only OpenAI preparation under the current Plugin Creator instructions.

## Facts still needed for public submission

| Item | Current state | Needed next |
| --- | --- | --- |
| Public plugin website | [Public showcase on AirbnbAI](https://airbnbai.rent/automate.html#airbnb-hosting-expert) | Use the confirmed URL in submission metadata |
| Support | [Published contact form](https://airbnbai.rent/?topic=airbnb-hosting-expert#contact) | Confirm the publisher can access submissions and select the support URL for submission metadata |
| Privacy policy | No URL in source | Confirm actual publisher practices and publish an applicable policy |
| Terms of service | No URL in source | Confirm applicable terms and publish them |
| Publisher verification | Existing package says Rachael Quisel | Confirm the intended verified publisher; the package name does not prove verification |
| Country targeting | Unspecified | Explicit countries or an explicit all-countries choice |
| Commerce | Unspecified | Confirm whether the plugin involves payments or purchases and, if so, what and where |
| Intended directory | Existing OpenAI/Codex package used | Confirm if Claude or both directories were intended |

Unknown values are omitted from metadata rather than invented. The included PRIVACY.md describes the inspected package and is not a published privacy policy. The public video showcase and contact route are now published on AirbnbAI; plugin-specific legal-policy pages remain unpublished. See [video and website documentation](video-showcase.md) for the publication checks.

## Behavioral verification limits

The following rules were checked in the revised source: missing listing text prompts for context; inaccessible public pages are not described as reviewed; an undecided reservation change is not presented as accepted; an unconfirmed repair is not described as finished; public review replies omit private guest details; credential and access-code requests are avoided; external account actions require a specific authorized tool action; current-policy statements require official sources.

The publisher subsequently ran a listing review on her own La Maison Airbnb listing and supplied the [complete output](../examples/la-maison-listing-review.md) on October 12, 2026. It includes six recommendations and proposed listing copy. This documents one publisher-reported usage example; the exact prompt and run version were not supplied, and the run was not independently replayed. It does not verify that changes were applied to the listing or that booking performance improved.

The remaining scenarios have not been run against the saved plugin in a fresh ChatGPT or Codex installation. Source coverage, component validation, saved-release readback, and host behavior are distinct checks. Public portal validation, developer verification, policy attestations, and directory review have not been performed.

## If Claude directory standards were intended

The existing OpenAI/Codex identity and format were preserved. A separate Claude package still needs a Claude manifest and marketplace manifest, a confirmed support location, and the publisher's license choice and corresponding LICENSE file. The current icon meets the Claude checklist's 1024 by 1024 target and observed size guidance. No Claude install or directory submission is claimed.

## Icon provenance

The icon was drawn using the Ghibli Icon Maker skill and its bundled renderer. The original geometry helpers, hand-wobble function, Sheet API, ground, and paper-grain functions were reused unchanged. One new guesthouse-and-message drawing function was added in the working copy. The official Airbnb logo SVG path was retrieved from the public homepage and rendered without hand-wobble. Its color came from the homepage's palette-rausch value, #FF385C. No AI image-generation tool was used for this replacement.

The exported PNG is airbnb-hosting-expert.png. The current package references assets/airbnb-hosting-expert.png for its listing and composer icons. Version 0.2.3 changes only these icon references, the asset, version, release notes, and changelog; saved hosting instructions and starter prompts were verified unchanged.
