# NEXA — Testing and Evidence Report

[Overview](README.md) · [Workflow atlas](NEXA_WORKFLOWS.md) · [Testing report](NEXA_TESTING_REPORT.md) · [Roadmap](NEXT_CASE_STUDY_PLAN.md)

**Updated: 15 October 2026**  
**Public target:** [nexa-public.netlify.app](https://nexa-public.netlify.app/)  
**Application source:** [nexa-public](https://github.com/yasmeenmh90-beep/nexa-public), revision [`0ea3dab`](https://github.com/yasmeenmh90-beep/nexa-public/commit/0ea3dab6cf02051e6d8ee9989542b55d0b5792e7)

This report distinguishes source/build checks, mocked backend tests, owner-confirmed behavior, visible recordings/screenshots and outstanding validation. It is not a complete security audit or accessibility certification.

## Current release: 15 October 2026

### Automated and static checks

| Check | Recorded result | What it establishes |
| --- | --- | --- |
| TypeScript compilation | Passed | Source/component type consistency |
| Vite production bundle | Passed | Public frontend bundles successfully |
| Backend tests | **10 passed** | Request handling and configured API payload behavior with OpenAI mocked |
| Static React render | Passed | Unique IDs, valid local anchors/assets, existing tour destinations and dialog labels |
| Motion lifecycle checks | Passed for the motion release | Reveal setup, reduced-motion/unsupported-observer fallback and listener cleanup |
| Deployment assets | Updated feature bundles detected on the public host | New client code reached the host; not a full browser interaction test |

Reproduce application checks from the source repository, not from this documentation-only repository:

```bash
npm ci
npm run typecheck
npm run build
node --test tests/chat.test.mjs
```

The test suite covers:

1. Forwarding bounded follow-up context while dropping extra history-item fields.
2. A first question without history.
3. Rejecting privileged roles, invalid order and oversized/malformed history.
4. Accepting the maximum permitted history.
5. Rejecting invalid messages and oversized payloads without an upstream call.
6. Disabled-chat and foreign-origin handling.
7. Generic upstream-throttling errors without leaking upstream error content.
8. Fixed interview track/level instructions and educational coaching boundaries.
9. Rejecting unsupported purposes and interview settings.
10. Keeping general chat separate from interview instructions.

Tests do **not** call a live model, validate coaching quality, prove Netlify’s deployed throttling behavior, or certify production security.

### Browser and owner-supplied observations

| Feature | Evidence available | Status / limit |
| --- | --- | --- |
| General Live AI answers | Owner reports successful written answers | User-confirmed |
| Follow-up context, copying and suggestions | Owner confirmed the requested visitor-tool tests worked | User-confirmed; no isolated per-control automated browser log |
| Speech recognition | Owner confirmed dictated text appeared after the recognition fix | User-confirmed; browser/provider dependent |
| Spoken replies | Owner reports audible replies; later screenshot displays Speaking / Voice playing | User-confirmed audio; screenshot proves UI state, not sound quality |
| Speaking halo and bars | Screenshots/recordings show playback visuals | Visually observed; no mouth synchronization |
| Guided tour | Recording shows opening and navigation between sections | Visually observed; full Back/Escape/focus/phone coverage still pending |
| Interview start | Recording shows the supervised-versus-unsupervised-learning question | Visually observed |
| Interview feedback | Screenshot shows a submitted answer, a Strength response and the start of an Improvement section | Visually observed |
| Next interview question after feedback | Not visible in the supplied final feedback screenshot | Still needs explicit verification |
| Current desktop presentation | Supplied scrolling recordings | No obvious overlap in sampled views; not frame-by-frame performance measurement |
| Current mobile/tablet and accessibility | Not comprehensively evidenced after the latest redesign | Pending device and assistive-technology review |

The October 15 recordings/screenshots were supplied in the project conversation. They are not embedded or publicly hosted by this documentation update. Do not infer unobserved outcomes from a screenshot of a control.

## Current network and data behavior

- **Sample Demo** selects fictional local replies and does not call OpenAI.
- **Live AI** sends a submitted message, bounded recent user/assistant history and selected experience settings to `/api/chat`. The server calls OpenAI.
- History is limited to six alternating messages, up to 2000 characters each and 6000 characters total.
- Reset, mode changes and refresh clear this app’s browser-held context. Interview track/level changes also start a new session.
- Browser voice recognition may use the browser provider’s speech service.
- Public chat does not connect to n8n, personal email/calendar services, private repositories or long-term memory.
- Feedback links open public GitHub issue drafts. They do not automatically submit an issue or attach conversation text.

The function source configures a 48,000-byte body limit, 1–1500-character current message, a 20-second upstream timeout, 400 output-token limit and a five-per-minute IP/domain rate limit. A configured origin check is not authentication; rate limiting is not an account-wide spending cap. Account budgets and deployed enforcement need separate review.

## Historical baseline: 13 October 2026

The following results belong to an **earlier fictional sample-only release**. They remain useful historical evidence, but are not current-release scores.

### Lighthouse

A supplied Chrome screenshot with the iPad Mini 768 × 1024 device preset visible reported:

| Category | Historical score |
| --- | ---: |
| Performance | 100 / 100 |
| Accessibility | 96 / 100 |
| Best Practices | 100 / 100 |
| SEO | 100 / 100 |

One audit run does not establish all-device performance or accessibility compliance. The screenshot did not include complete findings or conclusively identify the audit mode. These scores have **not** been rerun for the voice/interview/animation release.

### Ten historical sample observations

| Case | Recorded visible behavior |
| --- | --- |
| D01 · Daily briefing | Fictional priorities and tasks shown |
| D02 · Inbox | Example summary; no mailbox accessed |
| D03 · Calendar | Fictional design-review/planning events |
| D04 · Projects | Illustrative status; no project service queried |
| D05 · Career | Fictional opportunity, not a live vacancy |
| D06 · GitHub | Illustrative repository/issue update |
| D07 · Reset | Conversation cleared |
| D08 · Avatar previews | Visual state labels changed; audio was not part of that release |
| D09 · Unsupported request | Clear sample-demo fallback |
| D10 · Sensitive request | Sample fallback; no credentials displayed |

These **10 historical UI observations** are different from the **10 current automated backend tests**.

Historical Fetch/XHR captures showed zero matching entries during the demonstrated local sample actions. That does not mean the current Live AI site makes no network requests. A filtered snapshot also cannot exclude all other request types or security issues.

Earlier responsive captures included 320 px, 440 × 956 and 768 × 1024 views. The owner reported navigation and keyboard checks for that earlier version; those reports do not automatically transfer to the latest redesigned release.

## Remaining validation

- Complete one interview answer → feedback → next-question cycle in each intended track.
- Verify hints refer to the current question and general chat stays separate.
- Test Reset, mode/track changes and request cancellation while a reply is pending.
- Test the tour’s Back, Finish, Escape, focus trapping/restoration and small-screen placement.
- Check current 320–430 px phone layouts, tablets, zoom, focus order, contrast and screen readers.
- Test microphone denial/unavailability, unsupported recognition, audio failure and Stop speaking.
- Inspect current network behavior; verify no secret reaches browser bundles.
- Review deployed request limits, dependencies, Netlify credits and OpenAI spending settings.
- Rerun Lighthouse for the current release and publish dated findings if desired.

Private owner authentication, private n8n integration, approval-controlled actions and persistent memory remain outside the validated public scope. The separate portfolio/FlyRank audit results must not be presented as NEXA release scores.

## Related evidence

- [Workflow atlas](NEXA_WORKFLOWS.md): 18 historical workflow definitions and screenshot paths; editor state is not execution success.
- [Roadmap](NEXT_CASE_STUDY_PLAN.md): completed public work and future private integration.
- [Original FlyRank submission index](https://github.com/yasmeenmh90-beep/flyrank-ai-fluency-portfolio-docs/blob/main/FINAL_SUBMISSION_INDEX.md): earlier submission context.
