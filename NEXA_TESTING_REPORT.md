<!-- This document belongs to the dedicated NEXA public engineering case-study repository. The image archive is linked from the original FlyRank submission; the private portfolio source is maintained in a different private repository. -->

<div align="center">

<sub><strong>NEXA  /  PUBLIC SHOWCASE QUALITY ASSURANCE</strong></sub>

# ✦ NEXA Testing Report

### Functional Demonstration · Responsive Review · Lighthouse

Documented browser observations and user-supplied screenshots, with explicit distinctions between verified sample UI behavior and untested private integrations.

[![CORE DEMO: 10 OF 10 OBSERVED](https://img.shields.io/badge/CORE_DEMO-10_OF_10_OBSERVED-22c55e?style=flat-square)](https://nexa-public.netlify.app/) &nbsp; [![LIGHTHOUSE: 100 PERF](https://img.shields.io/badge/LIGHTHOUSE-100_PERF-8b5cf6?style=flat-square)](https://nexa-public.netlify.app/) &nbsp; [![ACCESSIBILITY: 96 OF 100](https://img.shields.io/badge/ACCESSIBILITY-96_OF_100-8b5cf6?style=flat-square)](https://nexa-public.netlify.app/)

**Yasmeen Azmat Ali** · 2026

[**NEXA Overview**](README.md) &nbsp;·&nbsp; [**Workflow Atlas**](NEXA_WORKFLOWS.md) &nbsp;·&nbsp; [**Testing Report**](NEXA_TESTING_REPORT.md) &nbsp;·&nbsp; [**Development Roadmap**](NEXT_CASE_STUDY_PLAN.md) &nbsp;·&nbsp; [**FlyRank Portfolio Evidence**](https://github.com/yasmeenmh90-beep/flyrank-ai-fluency-portfolio-docs/blob/main/FINAL_SUBMISSION_INDEX.md)

</div>

---

> **On this page:** [Scope](#01--test-scope) · [Lighthouse](#02--lighthouse-results) · [Demo cases](#03--public-demo-functional-results) · [Network observations](#04--network-and-privacy-observation) · [Limits](#06--outcome-and-boundaries)

---


> **Evidence standard.** This report records screenshots supplied by the project owner and the owner's report that all remaining navigation and accessibility checks passed on **October 13, 2026**. The Lighthouse scores are directly visible in a supplied Chrome screenshot. These observations **do not represent an independent penetration test or comprehensive accessibility certification**. Public n8n workflow screenshots are linked from the workflow atlas; screenshots documenting demo interactions and Lighthouse are available in the participant's submitted evidence and are not embedded in this Markdown document.

## 01 · Test scope

**Target:** [https://nexa-public.netlify.app/](https://nexa-public.netlify.app/)  
**Test period:** October 13, 2026  
**Application:** Public NEXA engineering case-study website, React / TypeScript / Vite / Tailwind CSS  
**Excluded:** Future owner-only application at `nexa.yasmeenazmat.com`, production identity verification, private n8n API integration and actual speech capabilities

The public showcase intentionally uses **fictional, locally predefined demo responses**, not live personal accounts or a private NEXA backend.

## 02 · Lighthouse results

A screenshot of the Chrome Lighthouse audit, taken while the browser's **iPad Mini 768 × 1024 device preset** was selected, shows:

| Audit category | Reported score | Interpretation |
|:---|---:|:---|
| Performance | **100 / 100** | Excellent score for this individual measured run |
| Accessibility | **96 / 100** | Strong automated score; review remaining audit findings |
| Best Practices | **100 / 100** | No deductions in the displayed Lighthouse category |
| SEO | **100 / 100** | No deductions in the displayed Lighthouse category |

These are **one-run Lighthouse scores**, not guarantees across all devices, network conditions, routes or future deployments. The screenshot does not show the underlying Accessibility findings or conclusively identify which Lighthouse mode was selected.

## 03 · Public-demo functional results

| Case | Tested behavior | Evidence and result |
|:---|:---|:---|
| D01 · Daily briefing | Displays fictional priorities, review and tasks | **Visually demonstrated** with a clearly labeled sample reply |
| D02 · Inbox | Displays example inbox summary | **Visually demonstrated**; disclaimer states no mailbox accessed |
| D03 · Calendar | Shows fictional design review and planning events | **Visually demonstrated**; fictional status stated |
| D04 · Projects | Displays illustrative project status | **Visually demonstrated**; no project-service read claimed |
| D05 · Career | Displays fictional applied-AI opportunity and next step | **Visually demonstrated**; not a live vacancy |
| D06 · GitHub | Displays illustrative repository and issue update | **Visually demonstrated**; no GitHub account access claimed |
| D07 · Reset | Clears conversation and restores welcome state | **Visually demonstrated** |
| D08 · Avatar states | Idle / Listening / Thinking / Speaking controls show distinct labels and visual cues | **Visually demonstrated**; no microphone recording or audio claimed |
| D09 · Unsupported request | Question about quantum computing produces clear predefined-demo fallback | **Visually demonstrated** |
| D10 · Privacy-sensitive request | Request for private access tokens produces the predefined-demo fallback; no secrets shown | **Visually demonstrated** |

**Core demo summary: 10/10 cases showed the expected visible behavior in user-provided screenshots.** These are *interaction-observation cases*, not ten independent automated unit or integration tests.

## 04 · Network and privacy observation

Chrome DevTools was opened on the deployed NEXA public URL, with the **Fetch/XHR** filter selected. During demonstrated sample actions, the captured table displayed **zero matching entries** (`0 / 4` in one screenshot; `0 / 5` in a separate mobile-demo screenshot).

- No private n8n requests were **visible in those filtered captures**.
- Visible sample responses consistently stated that no personal mailbox, repository, AI service or private integration was contacted.
- This provides **limited supporting evidence** for the browser-local demonstration boundary.

**Limit:** A filtered snapshot cannot exclude all other network request types, other sessions, extensions, security vulnerabilities or undisclosed server behavior. The private system was not connected or security-audited as part of this public showcase test.

## 05 · Usability, mobile and navigation

| Area | Evidence or report | Outcome |
|:---|:---|:---|
| **Mobile homepage** | Chrome responsive preview at **320 px**, plus iPhone 16 Pro Max **440 × 956** preset | Text and hero content visibly rearranged vertically; no obvious homepage clipping in captures |
| **Mobile demo** | Sample Daily Briefing reply, quick actions, avatar and composer visible at **440 × 956** | **Visually demonstrated** |
| **Tablet / external links** | iPad Mini **768 × 1024** browsing captures for GitHub, personal portfolio and LinkedIn | All three opened their destinations; LinkedIn prompted for sign-in |
| **FAQ interactions** | Three relevant FAQ answers expanded, including separation from private app and account data | **Visually demonstrated** |
| **Navigation anchors** | Owner reported all menu/anchor checks passed | **User-confirmed**; no per-link test log attached here |
| **Keyboard access and usability** | Owner reported all accessibility checks passed | **User-confirmed**; detailed key-by-key evidence not provided |
| **Lighthouse accessibility** | Chrome audit screenshot | **96 / 100** |

**Further review recommended:** Real-phone touch targets, keyboard focus order, screen-reader semantics, browser zoom, and the exact reason for the four-point accessibility deduction. In a few earlier screenshots the Demo heading was partially hidden under the sticky header at some scroll positions; verify anchor offsets in the final published build.

## 06 · Outcome and boundaries

The public NEXA showcase has a working, visually demonstrated **fictional sample-interaction experience**, a case-study narrative and clear public/private architecture disclosures. The participant reports completing navigation and manual accessibility checks; a Lighthouse run returned **100 Performance, 96 Accessibility, 100 Best Practices and 100 SEO**.

**Not yet implemented or not validated by this report:**

- Owner-only authentication and secure production session management
- Private React-to-n8n gateway integration and live specialist responses in the new website
- Real microphone capture, speech recognition, speech synthesis or lip synchronization
- Comprehensive security testing, accessibility compliance audit, and cross-browser/real-device certification

## 07 · FlyRank submission evidence

| Deliverable | Link / source |
|:---|:---|
| NEXA public engineering showcase | [nexa-public.netlify.app ↗](https://nexa-public.netlify.app/) |
| Second capstone continuation plan | [NEXT_CASE_STUDY_PLAN.md](NEXT_CASE_STUDY_PLAN.md) |
| This testing report | `NEXA_TESTING_REPORT.md` |
| Demo interaction, FAQ, mobile, external-link and Lighthouse screenshots | Owner-supplied submission/chat evidence; not uploaded publicly |
| NEXA private deployment | **Planned**, not a public deliverable |

---

## 08 · Relation to FlyRank FL-09 evaluation

This testing report evaluates the **NEXA public sample interface**, not the separate [FlyRank AI/ML portfolio](https://yasmeenazmat.com/) demonstrated in the [3:07 video](https://www.youtube.com/watch?v=45gVlp1G5Wk).

| Evidence | Actual recorded result | Evaluation boundary |
|:---|:---|:---|
| NEXA sample interaction cases | **10/10** visually observed behaviors | Screenshot-based UI checks; not automation or backend execution |
| NEXA Lighthouse | Performance **100**, Accessibility **96**, Best Practices **100**, SEO **100** | One displayed audit run; no exact mode or full findings provided |
| NEXA Fetch/XHR inspection | **0** entries matched the selected filter during captures | Cannot rule out other request types or sessions |
| NEXA n8n workflow atlas | **18** documented workflow designs, with images listed in [the workflow atlas](NEXA_WORKFLOWS.md) | Screenshots demonstrate routing designs and publication indicators, not end-to-end execution |
| FlyRank portfolio | Earlier PageSpeed desktop **98**, mobile **71–72** | Separate project and earlier build; do not combine with NEXA Lighthouse |

**No unsupported performance claims:** No measured agent task success rate, latency distribution, live-model accuracy, or controlled v2-versus-v1 comparison has been supplied. Therefore none is inferred from these screenshots. For the strict FL-09 reproducibility requirement, consult the [portfolio README's FL-09 assessment](https://github.com/yasmeenmh90-beep/flyrank-ai-fluency-portfolio-docs/blob/main/README.md): the full source remains private.

---

<div align="center">

**Built with care · Evaluated with evidence · Presented with transparency**

[**NEXA Overview**](README.md) &nbsp;·&nbsp; [**Workflow Atlas**](NEXA_WORKFLOWS.md) &nbsp;·&nbsp; [**Testing Report**](NEXA_TESTING_REPORT.md) &nbsp;·&nbsp; [**Development Roadmap**](NEXT_CASE_STUDY_PLAN.md) &nbsp;·&nbsp; [**FlyRank Portfolio Evidence**](https://github.com/yasmeenmh90-beep/flyrank-ai-fluency-portfolio-docs/blob/main/FINAL_SUBMISSION_INDEX.md)

<sub>FlyRank General AI Fluency · Yasmeen Azmat Ali · 2026</sub>

</div>
