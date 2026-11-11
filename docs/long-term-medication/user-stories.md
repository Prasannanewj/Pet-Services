# Agile User Stories

Story points are provisional Fibonacci estimates for team refinement. P0 is required for the initial pilot, P1 for expansion, and P2 for later validation. See [features](features.md) and [epics](epics.md).

## Shared Definition of Done

Every story is done when acceptance criteria and relevant edge cases pass automated or documented tests; accessibility, privacy, security, and role permissions are reviewed; required analytics avoid exposing clinical notes to marketing; documentation and support procedures are updated; and product acceptance is complete. Clinical, promotional, legal, and safety content receives the appropriate approval before release.

## Pet Owners

### PO-1: Set up a medication routine

**As a** pet owner<br>
**I want** to enter my pet's prescribed medication instructions and reminder time<br>
**So that** I can build a reliable daily routine.

- **Description:** Capture owner-entered instructions, schedule, and clinic contact without changing the regimen.
- **Acceptance criteria:**
  - **Given** prescription instructions, **when** I save required details, **then** the routine appears in the care plan.
  - **Given** I review the routine, **when** it is displayed, **then** I am prompted to check it against the prescription.
- **Edge cases:** Missing fields; invalid time; schedule or time-zone changes.
- **Dependencies:** Pet profile; reminder service; reviewed safety content.
- **Priority:** P0.
- **Story points:** 5.
- **Tags:** `pet-owner`, `medication`, `onboarding`.
- **Definition of Done:** Shared criteria plus validated schedule changes and accessible setup.

### PO-2: Record a scheduled dose

**As a** pet owner<br>
**I want** to record whether a scheduled dose was given, not given, or skipped<br>
**So that** my household has a shared history of what happened.

- **Description:** Record a self-reported outcome and optional note.
- **Acceptance criteria:**
  - **Given** a scheduled dose, **when** I save an outcome, **then** the record shows outcome, recorder, and timestamp.
  - **Given** a dose was not given or I am unsure, **when** I view help, **then** I am directed to prescription instructions or the veterinary team, not told to adjust the dose.
- **Edge cases:** Duplicate submission; conflicting update; incorrect record correction.
- **Dependencies:** Medication routine; shared-care permissions; audit history.
- **Priority:** P0.
- **Story points:** 5.
- **Tags:** `pet-owner`, `medication`, `safety`.
- **Definition of Done:** Shared criteria plus tested conflict prevention and correction.

### PO-3: Coordinate with another caregiver

**As a** pet owner<br>
**I want** to invite another caregiver to view and update my pet's routine<br>
**So that** we can coordinate care without relying on memory.

- **Description:** Share a care routine with an invited household member.
- **Acceptance criteria:**
  - **Given** an invitation, **when** the caregiver accepts, **then** they can see the latest authorized routine and dose status.
  - **Given** a caregiver records a dose, **when** another opens the routine, **then** the latest saved status and recorder are visible.
- **Edge cases:** Revoked or duplicate invitation; stale offline status; simultaneous updates.
- **Dependencies:** Identity and access management; PO-2.
- **Priority:** P0.
- **Story points:** 8.
- **Tags:** `pet-owner`, `caregiver`, `permissions`.
- **Definition of Done:** Shared criteria plus tested revocation, conflict handling, and stale-status warning.

### PO-4: Plan a refill

**As a** pet owner<br>
**I want** an estimate of remaining supply and a refill reminder<br>
**So that** I can contact my pharmacy or clinic before I run out.

- **Description:** Estimate supply using owner-entered quantity and schedule.
- **Acceptance criteria:**
  - **Given** supply and schedule, **when** I view refill details, **then** the estimate is labeled as an estimate.
  - **Given** I update supply, **when** it is recalculated, **then** the displayed estimate and reminder reflect the update.
- **Edge cases:** Unknown supply; changed schedule; inaccurate or zero quantity.
- **Dependencies:** Medication routine; reminder preferences.
- **Priority:** P1.
- **Story points:** 5.
- **Tags:** `pet-owner`, `refill`, `reminders`.
- **Definition of Done:** Shared criteria plus tested recalculation and clear language that the app does not authorize refills.

### PO-5: Receive a vaccination reminder

**As a** pet owner<br>
**I want** to record a vaccination date from my pet's records and receive a reminder<br>
**So that** I can discuss preventive care with my clinic.

- **Description:** Support owner-entered or authorized clinic-provided reminders.
- **Acceptance criteria:**
  - **Given** a date and selected reminder, **when** it is due, **then** I am prompted to contact my clinic.
  - **Given** the reminder, **when** I read it, **then** it does not claim a vaccine is clinically due or required.
- **Edge cases:** Missing or outdated records; rescheduled visit; reminder disabled.
- **Dependencies:** Reminder service; clinic contact details; approved language.
- **Priority:** P0.
- **Story points:** 3.
- **Tags:** `pet-owner`, `vaccination`, `reminders`.
- **Definition of Done:** Shared criteria plus reviewed wording and tested date edits.

### PO-6: Redeem an eligible offer

**As a** pet owner<br>
**I want** an eligible digital coupon with clear terms<br>
**So that** I can use a benefit at a participating location.

- **Description:** Display approved offer details and a usable coupon identifier.
- **Acceptance criteria:**
  - **Given** I am eligible and the offer is active, **when** I open it, **then** I see terms, expiration, and participating channels.
  - **Given** an expired or unavailable offer, **when** I open it, **then** it is not presented as redeemable.
- **Edge cases:** Already redeemed; unavailable location; eligibility changes.
- **Dependencies:** Promotion approval; eligibility rules; redemption partner.
- **Priority:** P0.
- **Story points:** 5.
- **Tags:** `pet-owner`, `coupon`, `redemption`.
- **Definition of Done:** Shared criteria plus tested eligibility and expiration.

### PO-7: Control communication preferences

**As a** pet owner<br>
**I want** to manage care reminders separately from promotional messages<br>
**So that** I receive the communications I choose.

- **Description:** Provide separate channel-specific preferences.
- **Acceptance criteria:**
  - **Given** I withdraw promotional permission, **when** saved, **then** promotional sending is suppressed after the approved propagation period.
  - **Given** I opt out of promotions, **when** I retain care reminders, **then** those preferences remain unchanged.
- **Edge cases:** Synchronization failure; conflicting preferences; queued message at opt-out.
- **Dependencies:** Consent service; messaging providers; CRM synchronization where used.
- **Priority:** P0.
- **Story points:** 5.
- **Tags:** `pet-owner`, `consent`, `privacy`.
- **Definition of Done:** Shared criteria plus send-time consent checks and synchronization failure alerts.

## Veterinarians

### VET-1: Review an owner-shared care summary

**As a** veterinarian<br>
**I want** to review an owner-shared medication and observation summary<br>
**So that** the owner's history can support our consultation.

- **Description:** Present a concise summary only when the owner chooses to share it.
- **Acceptance criteria:**
  - **Given** an owner shares a summary, **when** I access it, **then** I can see the selected date range, recorded outcomes, and observations.
  - **Given** the summary, **when** I read it, **then** owner-entered information is labeled as self-reported.
- **Edge cases:** No records; revoked access; incomplete or conflicting entries.
- **Dependencies:** Owner records; secure sharing; clinic access controls.
- **Priority:** P1.
- **Story points:** 5.
- **Tags:** `veterinarian`, `care-summary`, `privacy`.
- **Definition of Done:** Shared criteria plus tested owner authorization and self-report labels.

### VET-2: Provide access to reviewed education

**As a** veterinarian<br>
**I want** owners to access reviewed medication education<br>
**So that** they can reinforce our discussion without unsupported advice.

- **Description:** Make approved general education available alongside the care plan.
- **Acceptance criteria:**
  - **Given** approved education, **when** an owner opens it, **then** it identifies review status and directs clinical questions to their veterinary team.
  - **Given** withdrawn or superseded content, **when** the library is accessed, **then** the retired version is not presented as current.
- **Edge cases:** No approved content; outdated links; withdrawal.
- **Dependencies:** Veterinary medical review; content management; approval workflow.
- **Priority:** P0.
- **Story points:** 3.
- **Tags:** `veterinarian`, `education`, `compliance`.
- **Definition of Done:** Shared criteria plus verified publication and withdrawal controls.

### VET-3: Support appropriate help-seeking

**As a** veterinarian<br>
**I want** owners to see how to contact a clinic or emergency service<br>
**So that** they do not mistake the product for a monitored clinical service.

- **Description:** Display reviewed help language in medication and observation workflows.
- **Acceptance criteria:**
  - **Given** an owner records an observation, **when** the screen is viewed, **then** it states the log is not monitored.
  - **Given** an owner needs help, **when** contact options are opened, **then** clinic details and emergency guidance are available.
- **Edge cases:** No clinic number; clinic closed; potentially serious concern.
- **Dependencies:** Reviewed safety content; clinic contact details; support procedures.
- **Priority:** P0.
- **Story points:** 3.
- **Tags:** `veterinarian`, `safety`, `observations`.
- **Definition of Done:** Shared criteria plus veterinary review and tested missing-contact behavior.

## Clinic Managers

### CLINIC-1: Invite owners to the program

**As a** clinic manager<br>
**I want** a clinic-specific invitation link and QR code<br>
**So that** my team can introduce the program during normal visits.

- **Description:** Provide shareable, approved enrollment materials.
- **Acceptance criteria:**
  - **Given** an enrolled clinic, **when** I open materials, **then** the approved link, QR code, and talking points are available.
  - **Given** an owner enrolls through the link, **when** enrollment is recorded, **then** it is attributed to the clinic.
- **Edge cases:** Inactive clinic; expired link; declined enrollment.
- **Dependencies:** Clinic onboarding; approved materials; enrollment analytics.
- **Priority:** P0.
- **Story points:** 3.
- **Tags:** `clinic-manager`, `adoption`, `onboarding`.
- **Definition of Done:** Shared criteria plus tested attribution and inactive-clinic behavior.

### CLINIC-2: Manage clinic staff access

**As a** clinic manager<br>
**I want** to manage staff access by role<br>
**So that** only authorized team members can use clinic functions.

- **Description:** Support invitations, role assignment, and access removal.
- **Acceptance criteria:**
  - **Given** an authorized manager invites staff, **when** accepted, **then** only assigned permissions are granted.
  - **Given** removed access, **when** the staff member attempts a protected function, **then** access is denied.
- **Edge cases:** Expired invitation; staff at multiple clinics; last manager removed.
- **Dependencies:** Identity service; clinic roles; audit logging.
- **Priority:** P0.
- **Story points:** 5.
- **Tags:** `clinic-manager`, `permissions`, `security`.
- **Definition of Done:** Shared criteria plus tested role enforcement and revocation.

## Zoetis Marketers

### MKT-1: Create an offer for review

**As a** Zoetis marketer<br>
**I want** to create a promotion with eligibility, terms, and dates<br>
**So that** an approved offer can be presented consistently.

- **Description:** Author a structured draft promotion.
- **Acceptance criteria:**
  - **Given** authoring access, **when** I submit a complete draft, **then** it is routed for required reviews.
  - **Given** an unapproved promotion, **when** an owner views offers, **then** it is not displayed.
- **Edge cases:** Missing terms; invalid date range; material edit after approval.
- **Dependencies:** Offer data model; approval workflow; legal and regulatory review.
- **Priority:** P0.
- **Story points:** 5.
- **Tags:** `marketing`, `promotions`, `approval`.
- **Definition of Done:** Shared criteria plus tested validation and reapproval.

### MKT-2: Configure an eligible loyalty benefit

**As a** Zoetis marketer<br>
**I want** to configure an approved loyalty benefit with transparent terms<br>
**So that** eligible owners receive ongoing value.

- **Description:** Define benefit eligibility, availability, and redemption terms.
- **Acceptance criteria:**
  - **Given** an approved active benefit, **when** an eligible owner views it, **then** terms and usage are visible.
  - **Given** an inactive benefit or ineligible owner, **when** evaluated, **then** it is not presented as available.
- **Edge cases:** Benefit exhausted; eligibility changes; terms revised.
- **Dependencies:** Promotion management; eligibility rules; fulfillment partner.
- **Priority:** P1.
- **Story points:** 5.
- **Tags:** `marketing`, `loyalty`, `eligibility`.
- **Definition of Done:** Shared criteria plus approval that benefits are not contingent on prescribing decisions.

### MKT-3: Pause a promotion

**As a** Zoetis marketer<br>
**I want** to pause an active promotion<br>
**So that** an unavailable or incorrect offer stops reaching owners.

- **Description:** Provide an auditable operational control.
- **Acceptance criteria:**
  - **Given** authorized access, **when** I pause an offer, **then** it is no longer presented as available after the defined propagation period.
  - **Given** a paused offer, **when** I review history, **then** the actor and time are visible.
- **Edge cases:** Already-sent or cached offer; redemption attempted after pause.
- **Dependencies:** Promotion lifecycle; channel integrations; audit logging.
- **Priority:** P0.
- **Story points:** 3.
- **Tags:** `marketing`, `promotions`, `audit`.
- **Definition of Done:** Shared criteria plus tested propagation and documented treatment of issued coupons.

## Campaign Managers

### CAM-1: Build a consent-aware audience

**As a** campaign manager<br>
**I want** to define an audience using approved attributes and permissions<br>
**So that** a campaign reaches appropriate, consenting owners.

- **Description:** Create and preview a versioned segment.
- **Acceptance criteria:**
  - **Given** approved criteria, **when** I preview the audience, **then** aggregate size and refresh time are visible.
  - **Given** an owner lacks required permission, **when** the audience is activated, **then** that owner is excluded.
- **Edge cases:** Stale data; empty segment; consent withdrawn after creation.
- **Dependencies:** Segmentation; consent service; approved attributes.
- **Priority:** P1.
- **Story points:** 5.
- **Tags:** `campaign`, `segmentation`, `consent`.
- **Definition of Done:** Shared criteria plus tested suppression and stale-data warnings.

### CAM-2: Schedule and control a campaign

**As a** campaign manager<br>
**I want** to schedule, pause, and limit approved messages<br>
**So that** outreach is timely and does not overwhelm owners.

- **Description:** Configure approved content, channel, schedule, and frequency.
- **Acceptance criteria:**
  - **Given** approved content and an eligible audience, **when** scheduled, **then** messages are queued for the selected channel and time.
  - **Given** a pause or consent withdrawal, **when** queued messages are evaluated, **then** affected messages are suppressed.
- **Edge cases:** Provider outage; time-zone change; duplicate send; approval withdrawn.
- **Dependencies:** Approved content; provider; consent checks; campaign audit trail.
- **Priority:** P1.
- **Story points:** 8.
- **Tags:** `campaign`, `messaging`, `controls`.
- **Definition of Done:** Shared criteria plus tested suppression and failure handling.

### CAM-3: Run a controlled campaign test

**As a** campaign manager<br>
**I want** to compare an approved campaign with a control group<br>
**So that** I can evaluate its incremental effect.

- **Description:** Assign eligible owners to groups and capture exposure.
- **Acceptance criteria:**
  - **Given** an approved experiment, **when** owners are assigned, **then** assignment is stable and recorded.
  - **Given** the campaign ends, **when** results are reported, **then** test and control denominators and outcomes are separate.
- **Edge cases:** Consent withdrawal; small audience; assignment changes across channels.
- **Dependencies:** Campaign configuration; analytics; experimentation plan.
- **Priority:** P1.
- **Story points:** 5.
- **Tags:** `campaign`, `experimentation`, `analytics`.
- **Definition of Done:** Shared criteria plus documented assignment, exclusions, and interpretation limits.

## Data Analysts

### DATA-1: Monitor program adoption

**As a** data analyst<br>
**I want** a dashboard of clinic and owner activation<br>
**So that** I can identify participation changes.

- **Description:** Report enrollment, activation, and participation using agreed definitions.
- **Acceptance criteria:**
  - **Given** authorized access, **when** I open the dashboard, **then** metrics include numerators, denominators, and periods.
  - **Given** delayed source data, **when** I view it, **then** refresh time and known gaps are visible.
- **Edge cases:** Duplicate enrollment; incomplete clinic attribution; missing data.
- **Dependencies:** Clinic and owner events; metric definitions; access controls.
- **Priority:** P0.
- **Story points:** 5.
- **Tags:** `analytics`, `adoption`, `dashboard`.
- **Definition of Done:** Shared criteria plus source-event reconciliation and published definitions.

### DATA-2: Analyze coupon redemption

**As a** data analyst<br>
**I want** to distinguish coupon issuance, redemption, and reversal<br>
**So that** I can report reliable performance.

- **Description:** Provide a redemption funnel using confirmed partner events.
- **Acceptance criteria:**
  - **Given** coupon events, **when** I view the funnel, **then** eligible recipients, issued coupons, confirmed redemptions, and reversals are separate.
  - **Given** unreconciled partner events, **when** I review the report, **then** discrepancies are flagged rather than silently confirmed.
- **Edge cases:** Duplicate event; delayed redemption; later reversal.
- **Dependencies:** Redemption Tracking; partner reconciliation; event definitions.
- **Priority:** P1.
- **Story points:** 5.
- **Tags:** `analytics`, `coupon`, `redemption`.
- **Definition of Done:** Shared criteria plus tested deduplication and reconciliation.

### DATA-3: Evaluate engagement and safety guardrails

**As a** data analyst<br>
**I want** care engagement alongside opt-outs, complaints, and safety indicators<br>
**So that** leaders assess value without optimizing engagement alone.

- **Description:** Report aggregates and distinguish self-reported from confirmed events.
- **Acceptance criteria:**
  - **Given** authorized access, **when** I view engagement, **then** available guardrails for the same period are shown.
  - **Given** owner-entered medication outcomes, **when** reported, **then** they are labeled self-reported and not verified adherence.
- **Edge cases:** Small cohorts; missing safety data; restricted sensitive information.
- **Dependencies:** Care events; consent and safety workflows; data governance.
- **Priority:** P1.
- **Story points:** 5.
- **Tags:** `analytics`, `engagement`, `safety`.
- **Definition of Done:** Shared criteria plus reviewed access controls and documented data limitations.

### DATA-4: Assess AI recommendation quality

**As a** data analyst<br>
**I want** to measure recommendation relevance and approved-content checks<br>
**So that** the team can decide whether an AI pilot should continue.

- **Description:** Report sampled review results and recommendation engagement.
- **Acceptance criteria:**
  - **Given** a pilot, **when** sampled outputs are reviewed, **then** results identify the model and content version.
  - **Given** a failed approved-content check, **when** reported, **then** the designated team can investigate.
- **Edge cases:** Insufficient sample; missing model version; withdrawn source content.
- **Dependencies:** AI evaluation controls; approved review criteria; monitoring ownership.
- **Priority:** P2.
- **Story points:** 5.
- **Tags:** `analytics`, `ai`, `governance`.
- **Definition of Done:** Shared criteria plus documented sampling, ownership, and escalation.
