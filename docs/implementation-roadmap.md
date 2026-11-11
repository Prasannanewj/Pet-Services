# Implementation Roadmap and Feature Prompts

**Status:** Proposed sequencing based on `main` at `ba37a3864b482618b7c5e25aae41210e8cbe48f4`. The [repository assessment](architecture-summary.md) found no application code on the default branch. The [product backlog](product-backlog.md) and its existing GitHub issues remain the source of product requirements and OKR links; do not create duplicate issues.

## Prioritized implementation backlog

The sequence is indicative rather than a commitment. Stories in a feature issue are scoped by the linked sub-issues. Governance and measurement are prerequisites for a real pilot, not later add-ons.

| Order | Work | Existing issue(s) | Dependencies and exit criteria |
|---|---|---|---|
| 0 | Decide pilot scope, approved stack, identity, data handling, provider contracts, and experiment design. Scaffold a minimal application and CI with synthetic data. | Technical prerequisite; no existing issue | Decisions documented; app runs locally; automated checks pass; no production data or sends. |
| 1 | Enrollment; clinic settings | [#2](https://github.com/Prasannanewj/Pet-Services/issues/2), [#4](https://github.com/Prasannanewj/Pet-Services/issues/4) | Identity and clinic authorization decided; clinic workflow approval is recorded and enforced. |
| 2 | Profiles; consent; preferences | [#9](https://github.com/Prasannanewj/Pet-Services/issues/9), [#11](https://github.com/Prasannanewj/Pet-Services/issues/11), [#13](https://github.com/Prasannanewj/Pet-Services/issues/13) | Approved data and consent model; verified contact and withdrawal enforced. |
| 3 | Approvals; incident management | [#34](https://github.com/Prasannanewj/Pet-Services/issues/34), [#37](https://github.com/Prasannanewj/Pet-Services/issues/37) | Reviewer roles and incident service levels agreed; material edits invalidate approvals. |
| 4 | Education; reminders; contact and booking | [#16](https://github.com/Prasannanewj/Pet-Services/issues/16), [#22](https://github.com/Prasannanewj/Pet-Services/issues/22), [#25](https://github.com/Prasannanewj/Pet-Services/issues/25) | Approved content and workflows, consent, clinic-provided due dates, and provider or safe mock available; no unauthorized sends. |
| 5 | Participation; awareness feedback; adoption, outcome and awareness reporting | [#6](https://github.com/Prasannanewj/Pet-Services/issues/6), [#19](https://github.com/Prasannanewj/Pet-Services/issues/19), [#42](https://github.com/Prasannanewj/Pet-Services/issues/42), [#40](https://github.com/Prasannanewj/Pet-Services/issues/40), [#46](https://github.com/Prasannanewj/Pet-Services/issues/46) | Defined baselines, event definitions, mature cohorts, and source-verified outcome data. Establish measurement design before pilot launch. |
| 6 | Offer management; redemption; campaign measurement | [#28](https://github.com/Prasannanewj/Pet-Services/issues/28), [#30](https://github.com/Prasannanewj/Pet-Services/issues/30), [#44](https://github.com/Prasannanewj/Pet-Services/issues/44) | Approved terms, funding, eligibility, verification, control design and relevant partner agreements. |
| 7 | Relevance; optimization; offer relevance | [#49](https://github.com/Prasannanewj/Pet-Services/issues/49), [#51](https://github.com/Prasannanewj/Pet-Services/issues/51), [#53](https://github.com/Prasannanewj/Pet-Services/issues/53) | Approved content and offers, reliable consent and measurement, pilot gate passed. Review open PR #55 before working on US-25. |

Technical prerequisites do not yet have issues; add them only when the team agrees to track them. All outcome targets remain provisional.

## Delivery roadmap

| Window | Scope | Gate |
|---|---|---|
| Months 1-3 | Validate clinic demand, baseline, architecture and privacy; decide stack; establish local development, tests, CI and experiment design. | Named owners approve scope, data access, clinical and legal controls, and feasibility. |
| Months 4-6 | Build the clinic, consent, approval, education and reminder slice; onboard initial clinics; establish baseline and intervention/control assignment. | Security, clinical, legal, privacy and operational reviews pass; workflows and data quality meet agreed thresholds before real sends. |
| Months 7-9 | Expand onboarding and approved integrations; test eligible promotions and redemption; improve monitoring and reporting. | Continue only with acceptable workload, safety, adoption, data quality and early economics. |
| Months 10-12 | Assess mature 90-day cohorts and controlled economics; evaluate rules-based personalization and next investment. | Scale, revise or stop based on evidence, uncertainty, safety and operating cost. |

Timelines depend on approvals, staffing and vendor access; they are not delivery estimates.

## Feature-by-feature working protocol

Run **one prompt at a time**. Before each iteration, inspect current `main`, the linked issue and its sub-issues, open PRs and existing code; reconcile changes made since this plan. Ask for unresolved decisions that materially affect the design, especially stack, identity, consent and external integrations. Implement only the selected feature and necessary dependencies, use synthetic data and mock adapters until approved, add focused tests, run the relevant checks, and document behavior and outstanding blockers. Do not close an issue or claim production readiness merely because a prototype exists.

### Prompt 0: Foundation

> Analyze the current repository and existing issues. Before implementing, confirm the approved language/framework, hosting, authentication, data store, and pilot constraints. Once decided, build the smallest runnable application foundation with safe synthetic data, authorization scaffolding, automated tests and CI. Document setup and explicitly identify mocked or unapproved integrations. Do not send real messages or use real owner data.

### Feature prompts

For each prompt, apply the working protocol above and use the issue's existing story acceptance criteria and OKR links.

| Issue | Prompt |
|---|---|
| [#2](https://github.com/Prasannanewj/Pet-Services/issues/2) | Implement clinic enrollment for authorized staff, including review status and confirmation, with tests for validation and access. |
| [#4](https://github.com/Prasannanewj/Pet-Services/issues/4) | Implement authorized clinic workflow approval and change history; prevent unapproved workflows from sending. |
| [#9](https://github.com/Prasannanewj/Pet-Services/issues/9) | Implement minimal owner and pet profiles and contact verification; test required fields, authorization and data minimization. |
| [#11](https://github.com/Prasannanewj/Pet-Services/issues/11) | Implement purpose- and channel-specific consent capture with approved wording and timestamps; test enforcement. |
| [#13](https://github.com/Prasannanewj/Pet-Services/issues/13) | Implement preference management and marketing withdrawal; test suppression of subsequent and queued applicable sends. |
| [#34](https://github.com/Prasannanewj/Pet-Services/issues/34) | Implement role-restricted campaign approvals and audit history; block launch without required approvals and invalidate them on material edits. |
| [#37](https://github.com/Prasannanewj/Pet-Services/issues/37) | Implement incident assignment, severity, timestamps and overdue escalation using agreed service levels. |
| [#16](https://github.com/Prasannanewj/Pet-Services/issues/16) | Implement accessible, versioned and clinically approved vaccine education and clinic preview; test that unapproved content is not published. |
| [#22](https://github.com/Prasannanewj/Pet-Services/issues/22) | Implement clinic-due-date reminders with approval, consent, suppression and frequency checks; test invalid dates, withdrawal, and delivery failure. |
| [#25](https://github.com/Prasannanewj/Pet-Services/issues/25) | Implement approved clinic contact or booking links; do not represent a visit as booked without confirmation. |
| [#6](https://github.com/Prasannanewj/Pet-Services/issues/6) | Implement a clinic participation dashboard and support pathway with clinic-scoped access. |
| [#19](https://github.com/Prasannanewj/Pet-Services/issues/19) | Implement versioned awareness surveys and response capture using the agreed baseline and privacy controls. |
| [#42](https://github.com/Prasannanewj/Pet-Services/issues/42) | Implement clinic and owner adoption reporting using documented denominators, event definitions and access controls. |
| [#40](https://github.com/Prasannanewj/Pet-Services/issues/40) | Implement intervention/control vaccination reporting with verified outcomes, mature cohorts, lift, confidence intervals and missing-data reporting; validate edge cases. |
| [#46](https://github.com/Prasannanewj/Pet-Services/issues/46) | Implement baseline versus follow-up awareness reporting with survey versions, response counts and percentage-point change. |
| [#28](https://github.com/Prasannanewj/Pet-Services/issues/28) | Implement governed offer configuration with eligibility, funding, terms and approval gates; test expired and unapproved offers. |
| [#30](https://github.com/Prasannanewj/Pet-Services/issues/30) | Implement eligibility-checked redemption and verified, deduplicated records; test invalid, expired and repeated redemption. |
| [#44](https://github.com/Prasannanewj/Pet-Services/issues/44) | Implement controlled campaign contribution reporting with explicit costs, assumptions and missing-data handling. |
| [#49](https://github.com/Prasannanewj/Pet-Services/issues/49) | Implement rules-based content relevance using permitted data and approved content; test missing data and avoid clinical claims. |
| [#51](https://github.com/Prasannanewj/Pet-Services/issues/51) | Implement approved message-variant experiments with explicit control groups, engagement and opt-out reporting. |
| [#53](https://github.com/Prasannanewj/Pet-Services/issues/53) | Inspect PR #55 and current US-25 criteria, then implement eligible-offer display only after approvals and offer eligibility exist; preserve visible terms and clinical independence. |
