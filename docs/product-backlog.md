# Pet Services: Epics, Features and User Stories

This backlog translates the [product strategy and OKRs](product-strategy.md) into eight epics. Each story links to its parent epic and the key results it supports. Targets are provisional until baselines and pilot feasibility are confirmed.

## OKR Reference

| ID | Key result by month 12 |
|---|---|
| O1-KR1 | Increase verified vaccination completion within 90 days of the clinic-defined due date by 10% relative versus control. |
| O1-KR2 | Improve vaccine-awareness survey scores by 10 percentage points from baseline. |
| O2-KR1 | Onboard 50 clinics. |
| O2-KR2 | Achieve 70% monthly active participation among onboarded clinics. |
| O2-KR3 | Achieve median clinic satisfaction of at least 4/5. |
| O3-KR1 | Achieve 15% redemption among uniquely eligible owners receiving an offer. |
| O3-KR2 | Demonstrate positive incremental contribution in at least one controlled campaign. |
| O4-KR1 | Achieve 40% verified-contact opt-in among invited eligible owners. |
| O4-KR2 | Achieve 30% quarterly active engagement among opted-in owners. |
| O4-KR3 | Keep opt-outs below 3% per campaign. |
| O5-KR1 | Obtain required approvals for 100% of launched campaigns. |
| O5-KR2 | Resolve 95% of identified high-severity issues within agreed service levels. |

## Epic Portfolio

| Epic | Outcome | Linked OKRs | Proposed timing |
|---|---|---|---|
| [E1. Clinic onboarding and administration](#e1-clinic-onboarding-and-administration) | Clinics can join and operate the pilot with minimal friction. | O2-KR1-KR3 | Months 1-6 |
| [E2. Owner identity and consent](#e2-owner-identity-and-consent) | Owners can participate and control communications. | O4-KR1, O4-KR3; O5-KR1 | Months 1-6 |
| [E3. Vaccine education and awareness](#e3-vaccine-education-and-awareness) | Owners understand the value of veterinarian-recommended vaccination. | O1-KR2; O4-KR2 | Months 4-6 |
| [E4. Preventive-care reminders and action](#e4-preventive-care-reminders-and-action) | Owners receive timely, clinic-approved reminders and can contact their clinic. | O1-KR1; O4-KR2-KR3 | Months 4-9 |
| [E5. Promotions and redemption](#e5-promotions-and-redemption) | Eligible owners can discover and redeem appropriate offers. | O3-KR1-KR2 | Months 4-9 |
| [E6. Campaign governance and operations](#e6-campaign-governance-and-operations) | Marketing teams launch approved campaigns and manage incidents. | O4-KR3; O5-KR1-KR2 | Months 1-9 |
| [E7. Measurement and experimentation](#e7-measurement-and-experimentation) | Teams can evaluate care outcomes, adoption, and incremental value. | O1-KR1-KR2; O2-KR1-KR3; O3-KR1-KR2; O4-KR1-KR3 | Months 1-12 |
| [E8. Responsible personalization](#e8-responsible-personalization) | Communications become more relevant without compromising trust. | O3-KR1; O4-KR2-KR3; O5-KR1 | Months 7-12, subject to pilot gate |

## E1. Clinic Onboarding and Administration

**Features:** Clinic enrollment; clinic settings and participation.

| Story | Feature | User story | Acceptance criteria | Linked OKRs |
|---|---|---|---|---|
| US-01 | Enrollment | As a clinic manager, I want to enroll my clinic so that we can participate in the pilot. | Authorized staff can submit clinic details; the team can review enrollment status; the clinic receives confirmation when approved. | O2-KR1 |
| US-02 | Clinic settings | As a veterinarian, I want to approve my clinic's participating care workflows so that communications reflect our clinical approach. | Authorized clinic users can review and approve enabled workflows; changes are recorded; unapproved workflows cannot send. | O2-KR2 |
| US-03 | Participation | As a clinic manager, I want a simple view of participation and support options so that my team can use the platform efficiently. | Dashboard shows relevant activity and support contact; access is limited to authorized clinic users. | O2-KR2, O2-KR3 |

## E2. Owner Identity and Consent

**Features:** Owner and pet profiles; communication preferences.

| Story | Feature | User story | Acceptance criteria | Linked OKRs |
|---|---|---|---|---|
| US-04 | Profiles | As a pet owner, I want to provide my contact and pet details so that I can receive relevant information. | Required fields are clearly identified; contact verification is supported; only data needed for the pilot is collected. | O4-KR1 |
| US-05 | Consent | As a pet owner, I want to choose permitted communication channels so that I control how I am contacted. | Consent language is presented before opt-in; channel choices and timestamp are recorded; only permitted communications are sent. | O4-KR1, O4-KR3 |
| US-06 | Preferences | As a pet owner, I want to withdraw marketing consent so that unwanted communications stop. | Each applicable message provides an unsubscribe path; withdrawal is recorded and enforced for subsequent sends. | O4-KR3 |

## E3. Vaccine Education and Awareness

**Features:** Approved educational content; owner awareness feedback.

| Story | Feature | User story | Acceptance criteria | Linked OKRs |
|---|---|---|---|---|
| US-07 | Education | As a pet owner, I want clear information about vaccination so that I understand why my veterinarian recommends it. | Content is accessible, clinically reviewed, versioned, and directs owners to their veterinary team for individual advice. | O1-KR2, O4-KR2 |
| US-08 | Education | As a veterinarian, I want to review the education used in my clinic's journey so that it supports our care conversations. | Authorized clinic users can preview applicable content and its approval status before enabling it. | O1-KR2, O2-KR2 |
| US-09 | Awareness feedback | As a product analyst, I want to survey owner awareness using consistent questions so that I can compare results with baseline. | Survey version, audience, response counts, and scores are recorded; baseline and follow-up use the agreed measurement method. | O1-KR2 |

## E4. Preventive-Care Reminders and Action

**Features:** Clinic-approved reminders; clinic contact and booking.

| Story | Feature | User story | Acceptance criteria | Linked OKRs |
|---|---|---|---|---|
| US-10 | Reminders | As a clinic manager, I want reminders based on clinic-provided due dates so that owners are prompted at the appropriate time. | Reminders use an eligible pet's clinic-provided due date; missing or invalid dates do not trigger a send; consent and clinic approval are checked. | O1-KR1 |
| US-11 | Contact and booking | As a pet owner, I want to contact or book with my clinic from a reminder so that I can act conveniently. | The message provides the clinic's approved contact or booking link; the platform does not claim an appointment is booked unless confirmed by the booking system. | O1-KR1, O4-KR2 |
| US-12 | Reminders | As a pet owner, I want reminders to respect my preferences and frequency limits so that they remain useful. | Sends honor channel permissions and campaign frequency rules; opted-out owners are excluded from applicable marketing messages. | O4-KR2, O4-KR3 |

## E5. Promotions and Redemption

**Features:** Offer management; redemption verification.

| Story | Feature | User story | Acceptance criteria | Linked OKRs |
|---|---|---|---|---|
| US-13 | Offer management | As a marketing manager, I want to configure an eligible offer so that it reaches the intended audience. | Offer includes approved terms, dates, eligibility, category, and funding; it cannot launch without required approvals. | O3-KR1, O5-KR1 |
| US-14 | Redemption | As a pet owner, I want to understand and redeem an eligible offer so that I can access its benefit. | Terms and expiration are visible before redemption; eligible owners receive a unique code or approved redemption method; invalid or expired offers are rejected. | O3-KR1 |
| US-15 | Redemption | As a marketing analyst, I want verified redemptions recorded once per eligible owner so that performance is accurate. | Redemption records link to campaign and eligibility; duplicates are identified; unverified redemptions are reported separately. | O3-KR1, O3-KR2 |

Vaccine, medicine, and food offers require category-specific review. Food offers depend on suitable partner agreements; the backlog does not assume a Zoetis-owned food portfolio.

## E6. Campaign Governance and Operations

**Features:** Approval workflow; incident management.

| Story | Feature | User story | Acceptance criteria | Linked OKRs |
|---|---|---|---|---|
| US-16 | Approvals | As a medical or regulatory reviewer, I want to approve campaign content before launch so that communications meet applicable requirements. | Required reviewers and approval status are recorded; a campaign cannot launch while required approval is missing or invalidated by a material change. | O5-KR1 |
| US-17 | Approvals | As a marketing manager, I want an audit trail of campaign changes so that decisions and published content are traceable. | The trail records content version, editor, approval decisions, and launch time; authorized reviewers can access it. | O5-KR1 |
| US-18 | Incident management | As an operations lead, I want high-severity issues assigned and tracked so that they are resolved within agreed service levels. | Issues have severity, owner, timestamps, status, and resolution; overdue issues are visible for escalation. | O5-KR2 |

## E7. Measurement and Experimentation

**Features:** Outcome and adoption reporting; controlled campaign measurement.

| Story | Feature | User story | Acceptance criteria | Linked OKRs |
|---|---|---|---|---|
| US-19 | Outcome reporting | As a product analyst, I want to compare verified vaccination completion between intervention and control cohorts so that I can assess care impact. | Report shows eligible pets, verified vaccinations within 90 days, cohort rates, relative lift, sample sizes, confidence intervals, and missing-data rates. | O1-KR1 |
| US-20 | Adoption reporting | As a product owner, I want to see clinic and owner funnel metrics so that I can identify adoption barriers. | Report uses agreed definitions for onboarding, monthly active clinics, opt-in, engagement, opt-outs, and satisfaction; results can be filtered by reporting period. | O2-KR1-KR3; O4-KR1-KR3 |
| US-21 | Campaign measurement | As a marketing analyst, I want to compare campaign contribution with a control group so that I can evaluate incremental value. | Report identifies cohort assignment and shows incremental contribution alongside incentive, delivery, and campaign costs; assumptions and missing data are visible. | O3-KR2 |
| US-22 | Awareness reporting | As a product analyst, I want to compare awareness survey results with baseline so that I can evaluate educational impact. | Report shows survey version, response counts, baseline and follow-up scores, and the percentage-point change. | O1-KR2 |

## E8. Responsible Personalization

**Features:** Rules-based relevance; optimization experiments.

| Story | Feature | User story | Acceptance criteria | Linked OKRs |
|---|---|---|---|---|
| US-23 | Relevance | As a pet owner, I want to receive content relevant to my pet so that communications are useful. | Segmentation uses permitted, available data and approved content; missing data does not produce unsupported clinical claims. | O4-KR2, O4-KR3 |
| US-24 | Optimization | As a marketing manager, I want to test approved message variants so that we can improve engagement responsibly. | Variants are approved before use; audiences and controls are defined; results include engagement and opt-outs. | O4-KR2, O4-KR3; O5-KR1 |
| US-25 | Offer relevance | As a pet owner, I want to see offers for which I am eligible so that I am not presented with misleading promotions. | Eligibility rules are applied before display; offer terms remain visible; clinical advice is not replaced by promotional ranking. | O3-KR1 |

## Delivery Dependencies and Prioritization

| Priority | Deliverable | Prerequisites |
|---|---|---|
| P0: Pilot foundation | E1 enrollment, E2 consent, E6 approvals, E7 baseline and experiment design | Clinical, privacy, legal, data-access, and clinic participation decisions |
| P1: Preventive-care pilot | E3 education and E4 reminders | Approved content, clinic-defined due dates, consent, and clinic contact pathways |
| P1: Promotion pilot | E5 offer and redemption capabilities | Approved offer terms, funding, eligibility, and redemption verification |
| P2: Optimization | E8 personalization and expanded integrations | Reliable consent, data quality, pilot results, and approval workflows |

Epic success is measured by the linked OKRs, not story completion alone. The product owner should validate baselines, experiment size, and acceptance criteria with clinical, clinic, privacy, legal, and engineering stakeholders before committing the pilot scope.
