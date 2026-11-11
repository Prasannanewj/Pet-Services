# MVP, User Journey, and Mockups

## Customer Understanding

The problem is broader than forgetting: owners must establish a routine, administer medication, coordinate with others, and decide when to contact their veterinarian. Clinics have limited time and incomplete information between visits.

**Jobs to be done:**

- Help me know what is due and record what happened without relying on memory.
- Help me capture a change and know how to reach my veterinary team.
- Give everyone helping with care one shared picture of the routine.

Research with owners, veterinarians, and veterinary technicians should test whether shared records reduce uncertainty, owners value structured histories, and clinicians find concise owner-entered trends useful.

## MVP Scope

Start with US owners of dogs taking a daily oral chronic medication. Support one medication and one or more caregivers; complex schedules and injectables are later scope.

| Priority | Capability | Purpose |
|---|---|---|
| Must have | Pet profile, owner-entered instructions, schedule, and vet contact | Establish the routine and a path to help. |
| Must have | Reminders and shared log: given, not given, or skipped, with optional note | Support memory and handoffs. |
| Must have | Caregiver invitation and shared status | Reduce uncertainty about recorded doses. |
| Must have | Refill reminder using owner-entered supply and lead time | Prompt refill planning. |
| Must have | Observation log and shareable visit summary | Support recall and veterinary conversations. |
| Must have | Reviewed general guidance and clear help/contact options | Help owners navigate uncertainty safely. |
| Later | Practice integrations, pharmacy ordering, wearable data, injectable workflows | Avoid complexity before core value is proven. |

Caregivers see the latest shared status before recording. The service prevents conflicting records for the same scheduled dose and flags stale offline status. Refill dates are estimates, not authorizations. For a missed, refused, vomited, or incorrectly recorded dose, direct the owner to the prescription or veterinary team; never instruct them to repeat, double, or adjust a dose. Observations are not monitored. Owners choose whether to share summaries; there is no assumed monitored veterinary inbox or guaranteed response.

## Example Journey

1. Maya enters Milo's medication label instructions, reminder time, supply, and clinic number, then checks the prescription.
2. Maya invites Sam; both see the shared routine and latest status.
3. After administering the 8:00 AM dose, Maya records it as given; Sam sees who recorded it.
4. Maya notes that Milo was less active. The app provides clinic contact and says the log is not monitored.
5. Maya reviews and optionally shares a visit summary.
6. Before estimated supply runs low, Maya receives a reminder to contact the pharmacy or clinic.

## Low-Fidelity Mobile Mockups

### A. Today: shared routine

```text
+----------------------------------+
| Care Together             Milo v |
|                                  |
| TODAY                            |
|                                  |
| 8:00 AM                          |
| Daily medication                 |
| 1 tablet - As prescribed         |
|                                  |
| Status: Not yet recorded         |
| [ Record dose ]                  |
|                                  |
| Refill                           |
| Estimated 8 days of supply left  |
| [ View refill details ]          |
|                                  |
| [ Add observation ]              |
| Home    History    Care team     |
+----------------------------------+
```

### B. Record what happened

```text
+----------------------------------+
| < Record dose                    |
| Milo - Today, 8:00 AM            |
| Daily medication                 |
|                                  |
| What happened?                   |
| ( ) Given                        |
| ( ) Not given                    |
| ( ) Skipped                      |
|                                  |
| Note (optional)                  |
| [ difficult to administer      ] |
| [ Save record ]                  |
|                                  |
| Unsure what to do? Follow the    |
| prescription or call your vet.   |
| [ Call clinic ]                  |
+----------------------------------+
```

After saving, the home card shows, for example, **Given - recorded by Maya at 8:07 AM**. A record is a report, not proof the pet absorbed the medication.

### C. Add an observation

```text
+----------------------------------+
| < Add observation                |
| What did you notice?             |
| [ Less active than usual       ] |
| When? [ Today                v ] |
| [ Save observation ]             |
|                                  |
| This log is not monitored.       |
| Contact your vet with concerns.  |
| For severe or rapidly worsening  |
| symptoms, seek emergency care.   |
| [ Call clinic ]                  |
+----------------------------------+
```

### D. Visit summary

```text
+----------------------------------+
| < Milo's care summary            |
| Last 14 days                     |
|                                  |
| Medication records               |
| Given: 12 scheduled doses        |
| Not given: 1 - Skipped: 0        |
| No record: 1                     |
|                                  |
| Observations                     |
| Nov 10 - Less active than usual  |
| Nov 05 - Difficult to give dose  |
|                                  |
| Owner-entered information;       |
| not independently verified.      |
| [ Share summary ]                |
+----------------------------------+
```

## Pilot and Measurement

Test a clickable prototype with owners and clinicians, especially missed-dose and shared-care scenarios. Then run a small four- to six-week MVP pilot with veterinary partners. Measure owner-reported ease of care, activation, week-four engagement, shared-care use, veterinary usefulness, safety reports, and clinic burden. A recorded dose is a proxy for engagement, not verified adherence or a clinical outcome.
