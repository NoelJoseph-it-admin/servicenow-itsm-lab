---

# Lab 02 - Incident Management

An incident is an unplanned interruption to a service, or a reduction in its quality. The objective of incident management is to **restore service as quickly as possible**. This lab works a single incident through its full lifecycle in a live instance.

**Table:** `incident` · **Prefix:** `INC` · **Parent table:** `task`

---

## Part A - Full incident lifecycle

### Incident logged

| Field | Value |
|---|---|
| Number | `INC0010001` |
| Caller | Tina Enduser |
| Short description | Unable to log into Outlook - password rejected |
| Category / Subcategory | Inquiry / Help → Email |
| Impact | 3 - Low |
| Urgency | 2 - Medium |
| **Priority** | **4 - Low** (derived) |
| Assignment group | Service Desk – Auckland |
| Assigned to | Noel Analyst |

**Description as logged:** user unable to log into Outlook; had already restarted and re-entered credentials without success; issue began that morning.

### Priority is calculated, not chosen

Priority is derived from **Impact × Urgency** via a lookup table and is read-only on the form. Impact 3 × Urgency 2 returned Priority 4, matching the standard matrix:

| | Urgency 1 High | Urgency 2 Medium | Urgency 3 Low |
|---|---|---|---|
| **Impact 1 High** | 1 Critical | 2 High | 3 Moderate |
| **Impact 2 Medium** | 2 High | 3 Moderate | 4 Low |
| **Impact 3 Low** | 3 Moderate | 4 Low | 5 Planning |

**Impact** measures how much of the business is affected. **Urgency** measures how quickly it needs fixing. Deriving priority rather than letting it be typed prevents every caller's issue becoming a P1.

Priority auto-calculated from impact and urgency <img width="915" height="499" alt="evidence lab-02-01 priority-auto-calculated" src="https://github.com/user-attachments/assets/b7191949-4fd1-47bb-a33e-6c86e01c302b" />


### State progression

The incident was worked through the following states, each recorded in the audit trail:

```
New → In Progress → On Hold (Awaiting Caller) → In Progress → Resolved → Closed
```

`On Hold` requires an **On hold reason** - one of Awaiting Caller, Awaiting Change, Awaiting Problem, or Awaiting Vendor. Parking a ticket On Hold without a reason is a standard audit finding.

Resolution required two mandatory fields:

| Field | Value |
|---|---|
| Resolution code | Solution provided |
| Resolution notes | Password reset via self-service portal |

**Note on release differences:** the Australia release choice list does not include `Solved (Permanently)`, which appears in older ServiceNow documentation. `Solution provided` was selected because the fix was permanent - `Workaround provided` would imply the symptom was suppressed while the underlying cause remained, which is the signal to raise a Problem record.

Resolution codes are not cosmetic. They feed reporting, and a cluster of `Workaround provided` in one category indicates something broken underneath that nobody has raised a Problem for.

### Work notes vs Additional comments

| | Visible to | Used for |
|---|---|---|
| **Work notes** | Internal staff only | Diagnostics, what was checked and ruled out, handover detail |
| **Additional comments** | Caller, via portal and email | Updates and questions directed to the user |

This was validated by impersonating the caller and comparing the activity stream against the agent view.

**Agent view** - work notes present in the stream:

Agent view showing work notes <img width="914" height="500" alt="evidence lab-02-01 Agent View" src="https://github.com/user-attachments/assets/6aca1361-b96c-4f8a-9c7b-1fc320d443ca" />


**Caller view** (`View: Self Service`, impersonating Tina Enduser) - state changes, resolution detail and Additional comments are visible; the internal work note is absent:

Caller portal view without work notes <img width="914" height="500" alt="evidence lab-02-01 Caller-view" src="https://github.com/user-attachments/assets/a2d0c485-c0cd-4fba-8d86-9b677b3335dd" />


> **Takeaway:** the split between work notes and additional comments is the mechanism that keeps internal troubleshooting out of the customer's inbox. Posting diagnostic detail to Additional comments is a real and common mistake, and it is not reversible once the notification has sent.

### Self-audit: findings on my own ticket

Reviewing the completed record surfaced three things a team lead would flag:

1. **An internal status note ("Awaiting caller") was posted to Additional comments rather than Work notes**, making it customer-visible. Harmless in this instance, but the same error with diagnostic content is exactly how internal detail leaks to end users.
2. **Channel was left as `-- None --`.** This field records how the contact arrived - phone, email, self-service, chat - and drives reporting on contact volume by route, which is how a desk justifies headcount or investment in a portal.
3. **Location was left empty.** Relevant when triaging whether an issue is isolated or site-wide.

None of these break the ticket. All three degrade the data a service desk reports on, which is why ticket quality is audited separately from ticket resolution.

---

### Skills demonstrated

`Incident lifecycle` · `Impact/urgency prioritisation` · `On hold reasons` · `Resolution codes` · `Work notes vs customer-visible comments` · `Impersonation testing` · `Ticket quality self-audit`

