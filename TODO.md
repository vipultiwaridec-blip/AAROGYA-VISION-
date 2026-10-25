# Aarogya Vision delivery checklist

## Dashboard shell and visual system
- [ ] The application presents Aarogya Vision with the tagline “Smarter Reports. Better Decisions. Healthier Lives.” in a narrow left navigation rail and a light lavender workspace.
- [ ] The Overview dashboard derives displayed counts from the synthetic report data and includes report summary, Analyze New Report action, upcoming appointments, compact result cards, expandable test groups, trends, review findings, uncertainty indicators, recent reports, and next steps.
- [ ] Desktop, tablet, and mobile layouts keep cards readable, charts responsive, navigation usable, and controls touch-friendly without horizontal overflow.

## Report analysis and TrustLayer
- [ ] The app supports a demo report action plus a report intake modal for PDF selection and pasted report text; unsupported extraction is clearly explained rather than silently guessed.
- [ ] Result cards show test name, value/unit, reported interval, status text, mini trend where history exists, and an inspectable evidence action.
- [ ] Evidence panels show finding ID, source report, source page, extracted value, interval, status, source snippet, rule explanation, verification state, and limitations.
- [ ] The product visibly distinguishes extracted data, deterministic checks, educational rules, user verification, and clinician-only recommendations.

## Uncertainty, combinations, comparison, and visit prep
- [ ] The Uncertainty Radar identifies missing information and low-confidence fields using explicit labels and avoids unexplained medical certainty scores.
- [ ] Combination Detective is presented as a configured demonstration rule with its involved findings, limitations, version, and “Why did this match?” explanation.
- [ ] Change Detective compares two dated synthetic reports without fabricating prior values, flags non-diagnostic changes, and shows a dated trend chart.
- [ ] Doctor Visit Prep produces an informational print-ready summary with findings, limitations, supported questions, and clear non-diagnostic labeling.

## Doctor discovery and demo booking
- [ ] Find a Doctor supports specialty, location, consultation-type, and availability-oriented UI using synthetic demo profiles clearly labelled as demo data.
- [ ] Demo booking supports doctor selection, consultation type, date/time selection, required detail entry, review, explicit confirmation, conflict-safe slot handling, and a generated reference only after a successful backend response.
- [ ] My Appointments shows upcoming and completed/cancelled states plus booking status and demo reference; it never presents a simulated booking as real.

## Safety and quality
- [ ] Safety messaging is separate from routine discovery and states that severe or rapidly worsening symptoms require urgent assessment regardless of report analysis.
- [ ] `GET /api/health`, demo report, doctor, slot, appointment list, and appointment creation endpoints return structured responses and errors.
- [ ] Synthetic content is labelled fictional and not for clinical use; no unsupported diagnosis, treatment, emergency threshold, citation, provider capability, or real patient data is claimed.
- [ ] `pnpm check`, `pnpm test`, and `pnpm build` pass before delivery; the route manifest is served at `/manus-routes.json`.
