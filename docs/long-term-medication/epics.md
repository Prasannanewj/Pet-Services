# GitHub-Ready Epics

These are proposed Markdown descriptions, not new GitHub issues. Metrics establish a baseline during the pilot unless a target is explicitly approved. See [features](features.md) and [user stories](user-stories.md).

**Program-wide guardrails:** Veterinarians retain clinical decisions. Promotional consent is separate from care reminders. Medication and vaccination information is unverified unless confirmed by an authorized source. Observations are not monitored for emergencies.

## 1. Promotions Management

**Epic name:** Manage Approved Pet Care Promotions

**Business value:** Launch relevant, compliant offers consistently across participating channels.

**Problem statement:** Disconnected tools can produce inconsistent eligibility, terms, approval status, and expiration dates.

**Success metrics:** Draft-to-launch time; active offers with complete approved terms; ineligible or expired offers displayed.

**Dependencies:** Compliance & Audit; Redemption Tracking; approved terms and fulfillment partners.

**Risks:** Incorrect eligibility, outdated claims, regulatory restrictions, or compromised veterinary independence.

**Acceptance criteria:**
- Authorized users can draft, review, approve, schedule, pause, and retire an offer.
- Each offer has versioned eligibility, dates, terms, channels, and redemption rules.
- Only approved, currently valid offers are displayed to eligible recipients.
- Changes and approvals are auditable; benefits are not contingent on prescribing decisions.

## 2. Campaign Management

**Epic name:** Orchestrate Consent-Based Care Campaigns

**Business value:** Increase awareness and engagement through coordinated clinic and digital communications.

**Problem statement:** Teams lack a consistent way to coordinate messages, manage consent, and compare channel performance.

**Success metrics:** Enrollment and engagement rates; opt-outs; launch time; incremental response against a control where feasible.

**Dependencies:** Promotions Management; Customer Segmentation; CRM Integration; Compliance & Audit.

**Risks:** Excessive messaging, inappropriate targeting, consent violations, or confusion between promotions and care instructions.

**Acceptance criteria:**
- Authorized users create campaigns with approved content, audience, channel, schedule, and frequency limits.
- Promotional sends require valid channel permission and honor opt-outs.
- Service reminders and promotions have separate preference controls.
- Events record delivery, engagement, and exposure without implying a clinical outcome.
- Campaigns can be paused; content and audience versions are auditable.

## 3. Offer Personalization

**Epic name:** Deliver Relevant, Transparent Offers

**Business value:** Improve relevance and redemption while preserving choice and trust.

**Problem statement:** Generic offers may not match preferences, eligibility, or care stage.

**Success metrics:** Eligible-offer engagement; redemption among unique eligible recipients; opt-outs and complaints; incremental redemption versus control.

**Dependencies:** Promotions Management; Customer Segmentation; Compliance & Audit; Redemption Tracking.

**Risks:** Intrusive targeting, unfair exclusion, inaccurate data, or inappropriate health inference.

**Acceptance criteria:**
- Offers use approved eligibility rules and permitted owner-provided data.
- Owners can understand why an offer is shown and update preferences.
- Ineligible, expired, or exhausted offers are not presented as redeemable.
- Offers are not recommendations to start, stop, or change treatment.
- Effectiveness can be measured against an approved comparison group.

## 4. Customer Segmentation

**Epic name:** Build Privacy-Aware Customer Segments

**Business value:** Reach appropriate audiences with fewer irrelevant communications.

**Problem statement:** Fragmented customer data makes audiences difficult to define, refresh, and govern.

**Success metrics:** Segment setup time; recipients meeting eligibility criteria; consent-related exclusions; data freshness.

**Dependencies:** CRM Integration; Compliance & Audit; agreed definitions and permissions.

**Risks:** Stale data, overly narrow targeting, unauthorized sensitive-data use, or inaccurate exclusions.

**Acceptance criteria:**
- Authorized users define segments using approved attributes and view criteria.
- Segments exclude owners without required channel consent.
- Source, refresh time, and version are visible to authorized users.
- Users can preview aggregate audience size before activation.
- Access and changes are logged; unapproved attributes cannot be used.

## 5. Redemption Tracking

**Epic name:** Track Digital Coupon Redemption

**Business value:** Measure offer performance and improve redemption.

**Problem statement:** Coupon exposure, redemption, and reversal can be inconsistent across channels.

**Success metrics:** Unique redemptions / unique eligible recipients; failed redemption rate; partner reconciliation rate.

**Dependencies:** Promotions Management; fulfillment partners; Analytics Dashboard; Compliance & Audit.

**Risks:** Duplicates, fraud, delayed partner data, inconsistent definitions, or treating all redemptions as incremental.

**Acceptance criteria:**
- Eligible owners access a coupon with clear terms, expiration, and participating channels.
- Issuance, redemption, rejection, and reversal are recorded where supported.
- Processing is idempotent and enforces applicable limits.
- Reports distinguish issuance, unique recipients, confirmed redemptions, and reversals.
- Reconciliation failures are surfaced for investigation.

## 6. Veterinary Clinic Portal

**Epic name:** Enable Veterinary Clinics to Support Pet Owners

**Business value:** Increase clinic participation while helping owners maintain routines and prepare for visits.

**Problem statement:** Clinics need a low-effort introduction without an unmonitored clinical inbox.

**Success metrics:** Active clinics / enrolled clinics; invitations per active clinic; staff-reported burden; clinic retention.

**Dependencies:** Clinic onboarding and support; Compliance & Audit; approved education; owner-controlled sharing.

**Risks:** Added workload, unauthorized access, monitoring confusion, or disruption to practice systems.

**Acceptance criteria:**
- Authorized staff can access onboarding materials and a clinic-specific invitation link or QR code.
- Staff access is role-based and limited to necessary information.
- Owners explicitly choose whether to share a medication or observation summary.
- Monitoring status is clear; the MVP does not imply a monitored clinical inbox.
- Approved materials do not change prescribing decisions.

## 7. Analytics Dashboard

**Epic name:** Measure Program and Campaign Outcomes

**Business value:** Give teams a consistent view of engagement, adoption, and commercial performance.

**Problem statement:** Disconnected reporting obscures reach, engagement, redemption, and incremental impact.

**Success metrics:** Dashboard adoption; reporting completeness; event reconciliation; report production time.

**Dependencies:** Campaign Management; Redemption Tracking; Veterinary Clinic Portal; event taxonomy and governance.

**Risks:** Misleading denominators, double-counted events, privacy leakage, or interpreting self-report as verified adherence.

**Acceptance criteria:**
- Dashboards show awareness, participation, activation, engagement, and redemption with defined denominators.
- Self-reported actions are distinguished from confirmed events.
- Authorized users can filter by approved campaign, channel, and date range.
- Data freshness, known gaps, and definitions are visible.
- Marketing access does not expose identifiable clinical notes without explicit authorization.

## 8. CRM Integration

**Epic name:** Connect Consented Owner Engagement to CRM

**Business value:** Coordinate communications and reduce fragmented records.

**Problem statement:** Consent, activity, and preferences can become inconsistent across systems.

**Success metrics:** Integration success; consent synchronization latency; duplicate records; unresolved errors.

**Dependencies:** CRM access; Customer Segmentation; Compliance & Audit; identity and consent rules.

**Risks:** Incorrect identity matches, stale consent, unnecessary data transfer, or silent failures.

**Acceptance criteria:**
- Approved attributes, preferences, and consent synchronize through documented interfaces.
- Uncertain identity matches are routed for review.
- Opt-outs propagate within an agreed operational timeframe.
- Failed transfers are logged, surfaced, and retried according to defined rules.
- Clinical observations are not transferred for marketing use without an approved purpose and authorization.

## 9. AI Recommendation Engine

**Epic name:** Recommend Approved Content and Offers Responsibly

**Business value:** Improve relevance while reducing manual selection effort.

**Problem statement:** Broad communications may not reflect owner preferences or stage of care.

**Success metrics:** Recommendation engagement; sampled relevance and approved-content checks; safety incidents; opt-outs.

**Dependencies:** Offer Personalization; approved content library; Customer Segmentation; Compliance & Audit; AI governance.

**Risks:** Incorrect content, hidden bias, inappropriate health inference, or AI-generated clinical advice.

**Acceptance criteria:**
- Recommendations are limited to approved education and eligible offers.
- The system does not diagnose, recommend medication changes, or determine vaccination schedules.
- Owners can adjust preferences and opt out of promotional personalization.
- Test relevance, safety, and inappropriate exclusions before release.
- Teams can monitor, disable, and audit versions; failures do not produce unapproved content.

## 10. Compliance & Audit

**Epic name:** Govern Consent, Safety, and Promotional Compliance

**Business value:** Protect trust and enable safe, accountable operation.

**Problem statement:** Consent, approvals, access, and potential adverse events require consistent controls.

**Success metrics:** Campaign approval coverage; consent-processing timeliness; audit completeness; time to route potential safety reports.

**Dependencies:** Legal, regulatory, privacy, security, veterinary medical, pharmacovigilance, and customer-support teams.

**Risks:** Missed escalation, unauthorized messaging or access, incomplete audit trails, and jurisdiction-specific noncompliance.

**Acceptance criteria:**
- Marketing and service preferences are separate and can be changed or withdrawn.
- Promotional content and offers require documented review before publication.
- Access, approvals, changes, and consent updates are recorded in an access-controlled audit trail.
- Potential adverse-event reports are routed to the designated safety team under a documented process.
- Retention, deletion, incident response, and jurisdiction-specific requirements are operational before launch.
