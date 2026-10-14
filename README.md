# Airbnb Hosting Expert

<img src="assets/airbnb-hosting-expert.png" alt="Airbnb Hosting Expert icon" width="180" />

Current package version: **0.2.3**.

An independent assistant for short-term rental hosts who want clearer listings, useful guest messages, and practical hosting improvements.

## What it helps with

- Review supplied listing text and suggest accurate improvements.
- Draft check-in messages and reservation-change replies from confirmed details.
- Write concise, respectful responses to guest reviews.
- Prioritize communication, arrival, cleanliness, and amenity improvements.
- Check current official guidance when a question depends on Airbnb policy and browsing is available.

Start with one of the existing prompts:

- How can I improve my Airbnb listing?
- What should I do if I get a bad review?
- How do I attract more guests?

The assistant asks for details that affect the answer and then returns a draft or short action list. It does not promise higher ratings, bookings, or revenue.

## Watch it work

[![Airbnb Hosting Expert animation](assets/airbnb-hosting-expert-video-poster.webp)](assets/airbnb-hosting-expert-1920x1080.mp4)

Run Airbnb Hosting Expert to get a clearer title and description for your listing. Copy and paste the finished text into Airbnb.

[Watch on AirbnbAI](https://airbnbai.rent/automate.html#airbnb-hosting-expert) · [Download the video](assets/airbnb-hosting-expert-1920x1080.mp4) · [Video and website documentation](docs/video-showcase.md)

## Example from my own listing

I ran the plugin on my [La Maison listing](https://www.airbnb.com/rooms/9131840) in downtown Santa Barbara. It recommended a new photo order, a more specific title, shorter room descriptions, and clearer sleeping arrangements. It also drafted a new opening paragraph.

Its first recommendation was:

> **La Maison’s biggest opportunity is its first impression:** bring the hot tub, space for gathering, and downtown location forward.

[Read the full output, including all six recommendations and the suggested listing copy.](examples/la-maison-listing-review.md)

## Access and limits

This package contains skills, reference text, and an icon. It includes no MCP server, Airbnb account connection, executable scripts, hooks, booking tools, or messaging service. It cannot inspect a private reservation or change an Airbnb account on its own. Browsing requires the host application's tools. Advice and drafting do not authorize external actions.

Drafts use the host's confirmed facts. Proposed repairs, changes, and refunds are not described as completed. Guest and property access details are omitted from public replies. General hosting guidance does not replace professional legal, tax, or financial advice.

See [data handling](PRIVACY.md) for the package's processing model. This file describes the source; it is not a substitute for published policies or the host application's terms.

Airbnb Hosting Expert is an independent third-party assistant and is not endorsed by or associated with Airbnb, Inc. or its affiliates. Airbnb is a trademark of its respective owner.


## Package and documentation

- [Current plugin](https://chatgpt.com/plugins/plugin_c92d5838e8888191a91d00efe93ef5cd)
- [Download the 0.2.3 package](dist/airbnb-hosting-expert-0.2.3.zip)
- [Publisher readiness and remaining items](docs/publisher-readiness.md)
- [La Maison listing-review example](examples/la-maison-listing-review.md)
- [Changelog](CHANGELOG.md)
- [Third-party branding](THIRD_PARTY_NOTICES.md)

The source at the repository root uses the Agent Plugins format, with a Codex compatibility manifest. The downloadable ZIP matches the private plugin release's source and icon. The La Maison example documents one publisher-reported listing review. Public directory submission and testing of the other hosting workflows remain pending.
