# Features by Epic

**Priority:** P0 is required for a safe initial pilot; P1 is for the next release or pilot expansion; P2 is later, subject to validation. These are proposed priorities. See [epics](epics.md) and [user stories](user-stories.md).

## 1. Promotions Management

| Feature title | Description | Business outcome | User persona | Priority | Dependencies | Technical considerations | KPI impact |
|---|---|---|---|---|---|---|---|
| 1.1 Promotion authoring | Create offers with eligibility, terms, channels, dates, and limits. | Reduce inconsistent setup. | Marketing manager | P0 | Approved terms; Compliance & Audit | Structured versioned records and required-field validation. | Setup time; complete terms. |
| 1.2 Review and approval workflow | Route offers through required reviews. | Prevent unapproved promotions. | Compliance reviewer; marketing manager | P0 | Authoring; approval policy; audit logging | Role-based states, immutable history, reapproval after material changes. | Approval time; documented approval coverage. |
| 1.3 Promotion lifecycle controls | Schedule, pause, expire, and retire offers. | Reduce expired or unavailable offers. | Marketing manager | P0 | Review workflow; delivery channels | Time zones, concurrent updates, cache invalidation, availability checks. | Expired offers displayed; complaints. |

## 2. Campaign Management

| Feature title | Description | Business outcome | User persona | Priority | Dependencies | Technical considerations | KPI impact |
|---|---|---|---|---|---|---|---|
| 2.1 Campaign configuration | Configure approved messages, audiences, channels, schedules, and frequency limits. | Coordinate consistent outreach. | Campaign manager | P1 | Content; segments; consent | Versioned configuration, adapters, scheduling, caps. | Launch time; eligible reach. |
| 2.2 Consent-aware message delivery | Send promotions only through permitted channels. | Enable trusted engagement. | Pet owner; campaign manager | P0 | Consent; approved provider | Check consent at send time, suppress withdrawals, surface failures. | Sending incidents; delivery; opt-outs. |
| 2.3 Campaign experimentation | Compare approved campaigns with a suitable control. | Identify incremental impact. | Marketing analyst | P1 | Configuration; analytics definitions | Stable assignment, eligibility snapshots, control integrity, sample size. | Incremental engagement and redemption lift. |

## 3. Offer Personalization

| Feature title | Description | Business outcome | User persona | Priority | Dependencies | Technical considerations | KPI impact |
|---|---|---|---|---|---|---|---|
| 3.1 Rules-based offer matching | Match owners to approved offers using permitted attributes. | Improve relevance and eligibility. | Pet owner; marketing manager | P1 | Authoring; approved attributes; consent | Check eligibility at display and redemption; avoid unsupported inference. | Engagement; ineligible display rate. |
| 3.2 Preferences and transparency | Explain offer relevance and allow preference changes. | Build trust and reduce unwanted communications. | Pet owner | P1 | Consent; offer matching | Accessible explanations, propagation, separate care controls. | Preference completion; opt-outs; complaints. |
| 3.3 Prioritization and frequency controls | Rank eligible offers and limit repeat exposure. | Reduce promotional fatigue. | Pet owner; campaign manager | P1 | Matching; campaign rules | Deterministic tie-breaking, channel caps, expired-offer exclusion. | Engagement; repeat exposure; opt-outs. |

## 4. Customer Segmentation

| Feature title | Description | Business outcome | User persona | Priority | Dependencies | Technical considerations | KPI impact |
|---|---|---|---|---|---|---|---|
| 4.1 Approved audience builder | Define audiences using approved owner, pet, and program attributes. | Improve targeting and limit inappropriate use. | Marketing analyst | P1 | Governance; CRM; consent | Attribute allowlist, role-based access, versioned definitions. | Setup time; criteria compliance. |
| 4.2 Consent and eligibility suppression | Exclude owners lacking permission or eligibility. | Reduce unauthorized outreach. | Campaign manager; pet owner | P0 | Consent; eligibility rules | Refresh exclusions before activation and recheck at send time. | Consent incidents; ineligible-recipient rate. |
| 4.3 Segment preview and freshness | Show aggregate audience size, source, and refresh time. | Improve planning confidence. | Marketing analyst | P1 | Audience builder; reporting definitions | Small-group suppression, refresh-failure and stale-data warnings. | Campaign rework; stale segments. |

## 5. Redemption Tracking

| Feature title | Description | Business outcome | User persona | Priority | Dependencies | Technical considerations | KPI impact |
|---|---|---|---|---|---|---|---|
| 5.1 Digital coupon access | Present eligible coupons, terms, expiration, and channels. | Make approved offers easier to use. | Pet owner | P0 | Approved promotion; fulfillment partner | Accessible mobile display, secure identifiers, eligibility checks. | Coupon access and redemption. |
| 5.2 Redemption event processing | Record issuance, confirmed redemption, rejection, and reversal where supported. | Establish a reliable performance record. | Marketing analyst; partner | P0 | Coupon access; partner interface | Idempotency, usage limits, timestamps, explicit status. | Confirmed and duplicate redemption rates. |
| 5.3 Partner reconciliation | Compare coupon events with partner records and flag discrepancies. | Improve accuracy and resolve failures. | Commercial operations analyst | P1 | Event processing; partner agreements | Reconciliation windows, exceptions, reversals, audit history. | Reconciliation rate; resolution time. |

## 6. Veterinary Clinic Portal

| Feature title | Description | Business outcome | User persona | Priority | Dependencies | Technical considerations | KPI impact |
|---|---|---|---|---|---|---|---|
| 6.1 Clinic onboarding and invitations | Provide instructions, talking points, and a clinic link or QR code. | Increase clinic and owner participation. | Clinic manager; technician | P0 | Enrollment; approved materials; access | Clinic attribution, accessibility, link lifecycle. | Clinic activation; invitations. |
| 6.2 Owner-controlled care summary | Let owners share medication events and observations. | Improve veterinary conversations. | Pet owner; veterinarian | P1 | Care records; sharing consent; clinic research | Secure sharing, self-report labels, not-monitored notice. | Sharing rate; veterinarian usefulness. |
| 6.3 Medication and preventive-care reminders | Record prescribed schedules and vaccination dates from records and select reminders. | Help owners prepare for care. | Pet owner; technician | P0 | Onboarding; service preferences; reviewed content | Use entered dates without determining eligibility; time zones and edits. | Reminder setup; clinic contact after reminders. |
| 6.4 Shared-caregiver coordination | Invite caregivers to view and record scheduled medication events. | Reduce handoff uncertainty. | Pet owner; caregiver | P0 | Schedule; household permissions | Attribute records, prevent conflicts, flag stale offline status. | Caregiver participation; conflicting records. |

## 7. Analytics Dashboard

| Feature title | Description | Business outcome | User persona | Priority | Dependencies | Technical considerations | KPI impact |
|---|---|---|---|---|---|---|---|
| 7.1 Program adoption dashboard | Report clinic and owner enrollment and activation. | Make adoption visible. | Product manager; commercial leader | P0 | Clinic and owner events; definitions | Explicit denominators, deduplication, freshness, access. | Completeness; reporting time. |
| 7.2 Campaign and redemption dashboard | Report reach, engagement, coupon issuance, redemption, and reversals. | Improve commercial decisions. | Marketing analyst | P1 | Campaign events; redemption; reconciliation | Distinguish unique recipients, events, confirmed redemptions, and estimates. | Reporting time; reconciliation. |
| 7.3 Care engagement and guardrails | Report care engagement with opt-outs, complaints, and safety indicators. | Avoid optimizing engagement at the expense of trust. | Product manager; compliance lead | P1 | Care events; consent and safety workflows | Label self-report, restrict identifiable data, document gaps. | Week-four engagement; complaints; opt-outs. |

## 8. CRM Integration

| Feature title | Description | Business outcome | User persona | Priority | Dependencies | Technical considerations | KPI impact |
|---|---|---|---|---|---|---|---|
| 8.1 Identity and preference synchronization | Synchronize approved identifiers and communication preferences. | Reduce fragmented records. | CRM operations manager | P1 | CRM access; identity rules; privacy approval | Minimize data; review uncertain matches. | Duplicate records; synchronization success. |
| 8.2 Consent and opt-out synchronization | Propagate consent between product, CRM, and messaging systems. | Honor choices consistently. | Pet owner; compliance lead | P0 before CRM-enabled promotional sending | Consent; CRM and messaging interfaces | Authoritative source, propagation time, failure alerts, send-time checks. | Propagation latency; unauthorized sends. |
| 8.3 Integration monitoring and recovery | Surface failed transfers and support controlled retry. | Reduce silent loss and disruption. | CRM operations manager; support engineer | P1 | CRM integrations; support ownership | Idempotent retries, exception queues, alerting, audit logs. | Unresolved errors; resolution time. |

## 9. AI Recommendation Engine

| Feature title | Description | Business outcome | User persona | Priority | Dependencies | Technical considerations | KPI impact |
|---|---|---|---|---|---|---|---|
| 9.1 Approved-content recommendation pilot | Recommend reviewed education using permitted preferences. | Help owners find useful information. | Pet owner | P2 | Approved library; preferences; AI governance | Restrict outputs to approved content; no diagnosis or medication advice. | Content engagement; sampled relevance. |
| 9.2 Eligible-offer recommendation pilot | Rank already eligible offers for opted-in owners. | Test AI's promotional relevance. | Pet owner; marketing manager | P2 | Eligibility; consent; AI controls | Eligibility is a hard rule; provide non-AI fallback; avoid health inference. | Engagement; incremental redemption. |
| 9.3 Recommendation evaluation and controls | Evaluate quality and allow monitoring or disabling of a version. | Limit unsafe, biased, or ineffective recommendations. | AI product owner; compliance reviewer | P1 before either AI pilot | Governance; evaluation dataset; monitoring | Versioning, human review, bias checks, audit, rollback, escalation. | Review pass rate; incidents. |

## 10. Compliance & Audit

| Feature title | Description | Business outcome | User persona | Priority | Dependencies | Technical considerations | KPI impact |
|---|---|---|---|---|---|---|---|
| 10.1 Consent and preference management | Manage separate service and promotional permissions. | Support owner choice. | Pet owner; compliance lead | P0 | Approved language; messaging channels | Versioned records, withdrawals, channel preferences, propagation monitoring. | Processing timeliness; complaints. |
| 10.2 Adverse-event intake and escalation | Route potential reports received through supported channels to the safety team. | Support timely safety review. | Pet owner; safety specialist; support agent | P0 | Safety process; training; escalation policy | Defined channels, secure handling, alerts, handoffs; no false monitoring claims. | Routing time; overdue escalations. |
| 10.3 Audit trail and access controls | Record material changes to offers, campaigns, permissions, approvals, and access. | Enable accountability. | Auditor; security administrator | P0 | Identity; roles; retention policy | Tamper-resistant logs, least privilege, retention, minimal sensitive data. | Completeness; unauthorized access. |
| 10.4 Privacy and data lifecycle | Apply collection, retention, access, and deletion rules. | Protect trust and reduce exposure. | Pet owner; privacy officer | P0 | Data inventory; reviews; vendor agreements | Minimize and encrypt data; deletion workflows and required-retention exceptions. | Request completion time; retention exceptions. |
