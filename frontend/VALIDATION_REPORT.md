# Validation report

Validated 30 September 2026 with Node 24.19 and npm 11.9.

| Check | Result |
| --- | --- |
| TypeScript type checking | Passed |
| Unit and component tests | 48 passed across 3 files |
| Production build | Passed |
| Production isolation scan | Passed: development inference and scenario implementations absent |
| Chromium browser tests | 27 passed |
| Lockfile reinstall | `npm ci --ignore-scripts` passed |

Browser coverage includes functional navigation, URL-preserved filters, detail and relationship links, full digest copying, unavailable downloads and public generation, error/retry and malformed metadata states, keyboard navigation, and development-only mock inference behavior. All six views were checked at 1440, 390 and 720 CSS pixels for horizontal overflow and the selected axe WCAG 2 A/AA, 2.1 AA and 2.2 AA rules; no violations were reported. Twelve desktop/mobile screenshots are included in `screenshots/` and were visually reviewed against the Figma styling.

The 720 CSS-pixel checks exercise the layout equivalent of a 1440-pixel viewport at 200% zoom; native browser zoom was not separately tested. Reduced-motion behavior was exercised. Automated accessibility checks do not replace a manual screen-reader audit. Firefox and WebKit were not tested.

The main production JavaScript bundle is approximately 347 KB before compression / 104 KB gzip; CSS is approximately 12 KB / 3 KB gzip. Fonts are self-hosted, and the default snapshot is approximately 10 KB. No external font, analytics, inference or proprietary service request is required for the default application.

All displayed records and check outcomes are explicitly synthetic examples. Tests validate presentation and contracts, not model provenance or a real verification result. Loading a report never establishes a successful local verification. Public generation remains unavailable. A regression test additionally confirms that synthetic evidence is rejected in public-snapshot mode even when approval fields and a matching source revision are present.

Only the new `frontend/` tree is supplied. Existing Python training and verification code was not modified. The upstream Python test suite was not run for this isolated frontend delivery. `PROJECT_GOAL.md` and `project/goal_state.json` were absent from the supplied repository archive; maintainer-approved progress mapping, public metadata, release identities and execution instructions remain integration inputs. See `CHECKLIST.md` and `PR_HANDOFF.md`.
