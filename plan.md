# Aarogya Vision implementation plan

## Scope
Aarogya Vision is a polished, synthetic-data healthcare report intelligence dashboard for a hackathon demonstration. The first delivery prioritises the core user journey over decorative marketing pages: inspect a report, understand deterministic range checks, open evidence in the TrustLayer, review uncertainty, compare two dated synthetic reports, discover demo doctors, and complete a clearly-labelled demo booking flow.

## Implementation approach
- React + TypeScript frontend in `client/src`, using a single dashboard shell with section navigation rather than disconnected pages.
- Recharts for a responsive historical trend panel and compact sparkline cards.
- Express JSON endpoints for health, demo reports, doctors, slots, appointments, and demo analysis metadata. Appointment writes are intentionally in-memory and visibly labelled Demo Booking Mode because no verified booking provider is configured.
- Synthetic report values are the source of truth for all dashboard counts, statuses, evidence and comparison summaries. No external AI key is required.
- Upload action is a functional demo interaction: it accepts pasted text or a local file selection, shows the selected source, and keeps the demo analysis available as a safe fallback when OCR/PDF extraction is not configured.
- Evidence drawer separates extracted data, deterministic range check, configured educational rule, verification state and limitations.

## Design direction
Three candidate directions considered: **clinical editorial precision** (0.07), **quiet wellness minimalism** (0.05), and **technical observatory** (0.08). Chosen direction: **clinical editorial precision**.

- **Design Movement:** Contemporary clinical dashboard design with editorial hierarchy, disciplined spacing, and restrained data-visualisation surfaces.
- **Core Principles:** Evidence before interpretation; compact information density; calm, non-alarming status language; actions always explain what happens next.
- **Color Philosophy:** Navy and blue establish trust and navigation clarity; lavender creates a softer clinical workspace; cyan is reserved for verified/evidence accents; amber flags review without panic.
- **Layout Paradigm:** Narrow navigation rail plus a spacious asymmetric workspace: a report summary band at the top, a dense results rail, and a large trend/evidence area to the right.
- **Signature Elements:** Monogram mark in a rounded square; tiny status dots paired with explicit labels; evidence links styled as quiet underlined actions.
- **Interaction Philosophy:** Every card is inspectable. Clicking a result opens its evidence trail. Booking and report analysis use short, explicit steps with clear demo states.
- **Animation:** Use subtle 160–220ms fades and slight elevation on hover. No looping decorative motion; charts draw attention only when the data changes.
- **Typography System:** Inter/system sans for reliable readability; 12px eyebrow labels, 14px body, 20–30px titles, 44px metric figures. Use medium weight more often than bold.
- **Brand Essence:** A trustworthy companion for making lab reports easier to discuss with a clinician. Calm, transparent, practical.
- **Brand Voice:** Headlines are clear and grounded; CTAs say what will happen. Examples: “See what changed” and “Open evidence trail”.
- **Wordmark & Logo:** AV monogram with a split vertical stroke suggesting a report column and a care pathway.
- **Signature Brand Color:** Deep report navy `#173B73`.

## Project structure
- `client/src/pages/Home.tsx`: dashboard shell, section views, evidence drawer, report modal, booking modal and local application state.
- `client/src/index.css`: complete visual system and responsive layout.
- `server/_core/index.ts`: health endpoint plus demo report, doctors, slots and appointment endpoints.
- `public/manus-routes.json`: route manifest for the dashboard shell.
- `TODO.md`: acceptance-oriented delivery checklist.

## Material constraints
All medical values, clinicians, appointments and rules are fictional demonstration content and must remain labelled as such. No diagnosis, emergency threshold, verified doctor, live slot or provider booking is claimed. The product includes safety copy advising urgent assessment for severe or rapidly worsening symptoms regardless of report analysis.

## Build workflow
Run host-managed TypeScript diagnostics, start the configured `pnpm dev` server on port 3000, verify `/api/health` and `/manus-routes.json`, run `pnpm check`, `pnpm test`, and `pnpm build`, then capture a desktop and mobile Preview screenshot for visual review before checkpointing.
