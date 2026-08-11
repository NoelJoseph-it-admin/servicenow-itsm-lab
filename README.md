# ServiceNow ITSM Lab

I am currently learning ServiceNow and IT Service Management (ITSM).

### **Lab 01, Part A: Lists, filters and the condition builder**

### 1. User Account Creation
- Created user accounts in ServiceNow.
- Practised basic user administration.
- Instance: dev420526.service-now.com
Release: Australia (latest)
Provisioned: 05/08/2026

### 2. System Statistics
- Used `stats.do` to explore ServiceNow system information.
- Practised navigating the ServiceNow platform.
- <img width="917" height="501" alt="evidence lab-00_stats-do" src="https://github.com/user-attachments/assets/102a6134-948c-4356-a163-594bde44d897" />

### 3. Conditional Builder
- Practised creating conditions.
- Explored fields, operators, and values.
- Learned how conditional logic works in ServiceNow.
- <img width="916" height="499" alt="evidence lab-01-02 conditional builder" src="https://github.com/user-attachments/assets/1d6860fb-fc1f-4eee-8e7f-ea9646121983" />

## Skills

- ServiceNow
- ITSM
- User Administration
- Conditional Builder
- System Administration

### **Lab 01, Part B: Forms, related lists, audit history**

- Explored the four zones of the incident form: header/UI actions, fields,
  activity stream, related lists
- Used the reference field preview (ⓘ) to open a caller record without leaving the form
- Configured form layout to surface an additional field
- Copied a record sys_id and confirmed it is the true identifier, with INC number as label
- Reviewed the audit history to see field-level changes with user and timestamp

**Takeaway:** ServiceNow audits every field change, so "who reassigned this ticket
and when" is always answerable from the record itself.

---

### **Lab 01, Part C: Users, groups, roles, impersonation**

Built and validated role-based access control end to end.

**Users created:**
| User ID | Name | Roles |
|---|---|---|
| `noel.analyst` | Noel Analyst | `itil` (inherited via group) |
| `tina.enduser` | Tina Enduser | none — end user |

**Group created:** `Service Desk – Auckland`
- Members: `noel.analyst`
- Roles: `itil`

**Validation via impersonation:**
- Impersonated `tina.enduser` → no incident queue visible, restricted self-service view only
- Impersonated `noel.analyst` → full incident queue visible

This confirmed the access model: roles are granted to groups, users inherit roles
through group membership, and effective permissions are the sum of all roles from
all groups a user belongs to.

**Evidence:** <img width="914" height="502" alt="evidence lab-01-03 enduser_view" src="https://github.com/user-attachments/assets/69a308df-9386-4370-adea-9c5c709cf2ae" />
<img width="916" height="502" alt="evidence lab-01-03 itil_view" src="https://github.com/user-attachments/assets/47d4cd48-7218-42cd-bc8b-766cab458935" />



**Takeaway:** when a new starter reports "I can't see any tickets," the first two
checks are whether they hold the `itil` role and whether they are in the correct
assignment group. Impersonation diagnoses this in seconds without needing their
password.

---

### **Lab 01, Part D: Module map + Service Operations Workspace**

Distinguished the SOW *view* (a column layout applied to the classic incident list)
from the SOW *workspace* (`/now/sow/home`) - a separate tabbed agent interface with
no application navigator or breadcrumb.

Viewed the workspace as admin first (all widgets empty - the admin account has no
assigned incidents and belongs to no assignment groups), then impersonated an agent
with a live queue: 5 incidents in progress, 1 breached SLA, 2 unassigned.

**Takeaway:** the workspace surfaces a breached SLA in two places simultaneously -
the SLA tile and the Upcoming panel. Escalation prompts are designed to be hard to
miss. For queue work the workspace beats the classic list because the caller's
history sits beside the record instead of two clicks away.

**Evidence:** <img width="916" height="497" alt="evidence lab-01-04 Service Operation Workspace" src="https://github.com/user-attachments/assets/9b040d8d-bf57-49c2-8b7d-54541ccb8f33" />

### Next up

- [ ] Lab 02 — Incident Management
