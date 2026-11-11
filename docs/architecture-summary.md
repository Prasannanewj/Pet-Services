# Repository Assessment and Architecture Summary

**Assessment baseline:** `main` at `ba37a3864b482618b7c5e25aae41210e8cbe48f4`, reviewed 2026-11-11. This describes the repository, not all systems or capabilities that may exist elsewhere at Zoetis.

## What exists

| Evidence | Finding |
|---|---|
| `README.md` | Entry point to product planning documents. |
| `docs/product-strategy.md` | Proposed vision, OKRs, risks, guardrails, and 12-month product roadmap. |
| `docs/product-backlog.md` | Eight epics, features, 25 user stories, acceptance criteria, and OKR references. |
| GitHub Issues | Eight epic issues, 21 feature issues, and 25 story issues, linked as epic > feature > story; all were open when reviewed. |
| Repository tree on `main` | No application source, dependency manifests, database migrations, test suite, deployment configuration, or repository-defined CI workflows. |

GitHub lists two active dynamic Copilot workflows; these are not repository-defined application CI workflows. The open [PR #55](https://github.com/Prasannanewj/Pet-Services/pull/55) changes US-25 acceptance criteria in the backlog only; it does not implement offer display. Do not treat it as merged or the feature as complete.

**Conclusion:** There is no existing application architecture or running implementation to document on the default branch. The current backlog is a product plan, not evidence that capabilities have been built. The [delivery backlog and roadmap](implementation-roadmap.md) adds technical prerequisites and a feature-by-feature implementation sequence without duplicating the existing issues.

## Proposed architecture: not yet implemented

Use the smallest deployable application that meets pilot needs, with clear domain boundaries rather than premature microservices. Hosting, programming language, framework, database, identity provider, and vendor choices are **undecided**. Confirm enterprise standards and integrations before selecting them.

```text
Owners, clinic staff, reviewers, marketing and operations
                         |
              Accessible web interface
                         |
        Application/API + authorization
         |       |        |         |
      Clinic  Consent  Campaigns  Reporting
      & pets  & prefs  & offers  & experiments
         |       |        |         |
      Durable data + audit records + controlled event capture
         |                |                |
   Clinic data/PIMS   Messaging provider   Redemption/analytics
     (as approved)    (consent-checked)   (as approved)
```

### Boundaries and responsibilities

| Boundary | Proposed responsibility | Key constraint |
|---|---|---|
| Identity and access | Authenticate users and authorize owner, clinic, reviewer, marketing, and operations roles. | Enforce clinic/tenant isolation on the server; access design and identity provider require approval. |
| Clinic and pet records | Manage enrollment, clinic-approved workflows, owner/pet linkage, and clinic-supplied due dates. | Do not infer clinical schedules or claim records are verified without a source. |
| Consent and messaging | Record purpose/channel permissions and withdrawals; route approved messages. | Recheck permission and suppression at send time, including queued messages; distinguish care messages from marketing according to approved policy. |
| Content and campaigns | Manage content versions, review decisions, campaign lifecycle, and offer terms. | No campaign may launch without all applicable approvals; material changes invalidate relevant approval. |
| Offers and redemption | Evaluate approved eligibility, expose terms, and record verified redemption. | Fail closed on missing eligibility or approval; food partnerships and medicine-specific rules remain unvalidated. |
| Measurement | Capture defined events, cohorts, care outcomes, and campaign costs for controlled reporting. | Report missing data and uncertainty; avoid claiming causality without a valid experiment. |
| Integration | Connect clinic records, booking, messaging, and redemption through approved adapters. | Provider contracts, data sharing, security, error handling, and operational ownership must be agreed first. |

### Illustrative data and flow

Potential entities include clinic, authorized user, owner, pet, contact verification, consent record, due date, approved content version, campaign, offer, eligibility decision, delivery, redemption, cohort assignment, and verified vaccination. Their fields, relationships, retention, and source-of-truth ownership are not yet designed.

An illustrative reminder flow: a clinic supplies a due date and approves the workflow; the application checks content approval, contact permissions, suppression, and frequency rules; a provider sends the message; the owner uses a clinic-approved contact link; and a separately verified clinical outcome feeds cohort reporting. Provider failure, withdrawal, late or corrected data, and auditability must be handled explicitly.

### Cross-cutting controls

- Privacy-by-design: data minimization, purpose limitation, access logging, retention/deletion policy, secure transport and storage, and incident response.
- Clinical and promotional governance: reviewed content, versioned approvals, role separation, documented claims and offer terms; no diagnosis or automated treatment advice.
- Reliability: observable delivery and provider failures, idempotent processing where relevant, backups and recovery, and clear operational ownership.
- Quality: automated tests for authorization, tenant isolation, consent withdrawal, approval gates, eligibility, and metric definitions; accessibility testing and safe synthetic test data.
- Measurement: versioned definitions for eligible populations, unique counts, mature 90-day cohorts, relative lift and percentage-point difference, and experiment controls.

## Decisions and unknowns before implementation

1. Product and clinical owners must approve pilot scope, roles, country-specific content, and communication categories.
2. Security and technology owners must select or approve the stack, hosting, identity, data storage, environments, and deployment process.
3. Privacy and legal owners must approve data flows, consent wording and purposes, retention, messaging rules, and partner contracts.
4. Clinic partners must establish access to due dates, verified outcomes, booking links, and approved communication workflows.
5. Analytics owners must determine baseline, randomization unit, sample size, data quality thresholds, and reporting approach.
6. Commercial owners must define offer eligibility, verification, funding, and food partner arrangements.

Until these decisions are made, use synthetic data and mocked adapters for local development; do not send real messages or process real customer records. A mock is not production readiness.
