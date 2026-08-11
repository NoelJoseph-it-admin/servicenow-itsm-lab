# ServiceNow Service Desk Lab — 7 Hour Practical Path

Hands-on ServiceNow ITSM lab work completed in a free Personal Developer Instance (PDI), documented for Service Desk Analyst / IT Support roles.

**Author:** Noel Joseph · Auckland, New Zealand
**Platform release used:** _(record yours — see Setup)_
**Instance:** `devXXXXXX.service-now.com` (personal developer instance)

---

## Why this repo exists

Most entry-level service desk job ads in New Zealand list ServiceNow as a required or preferred tool. This repo is proof of hands-on capability: every lab below was performed in a live ServiceNow instance, with screenshots and record numbers as evidence.

The scope is deliberately narrow. It covers the ~20% of ServiceNow that generates ~80% of a Tier 1/Tier 2 analyst's daily work: **working incidents, fulfilling requests, using knowledge, raising changes, and reading the CMDB.** It does not cover scripting, integrations, or implementation work — those belong to a CSA/developer path, not a service desk path.

---

## The 7-hour timetable

Do it in one Saturday, or split across three evenings. Timings assume you type the steps rather than read them.

| Block | Time | Topic | File |
|---|---|---|---|
| 0 | 0:00 – 0:25 | Developer account, PDI request, first login | [00-SETUP.md](00-SETUP.md) |
| 1 | 0:25 – 1:30 | Platform navigation, users, groups, roles, impersonation | [labs/LAB-01-navigation-and-admin-basics.md](labs/LAB-01-navigation-and-admin-basics.md) |
| 2 | 1:30 – 3:00 | **Incident Management** — full lifecycle, the core skill | [labs/LAB-02-incident-management.md](labs/LAB-02-incident-management.md) |
| 3 | 3:00 – 4:00 | Service Catalog, REQ / RITM / SCTASK, approvals | [labs/LAB-03-service-catalog-and-requests.md](labs/LAB-03-service-catalog-and-requests.md) |
| 4 | 4:00 – 4:35 | Knowledge Management, KCS basics | [labs/LAB-04-knowledge-management.md](labs/LAB-04-knowledge-management.md) |
| 5 | 4:35 – 5:20 | Change Management + Problem Management | [labs/LAB-05-change-and-problem.md](labs/LAB-05-change-and-problem.md) |
| 6 | 5:20 – 6:20 | CMDB, SLAs, reports, dashboards | [labs/LAB-06-cmdb-sla-and-reporting.md](labs/LAB-06-cmdb-sla-and-reporting.md) |
| 7 | 6:20 – 7:00 | Write-up, push to GitHub, interview drill | [notes/INTERVIEW-PREP.md](notes/INTERVIEW-PREP.md) |

**Block 2 is the one that matters most.** If you run short on time, never cut it. A hiring manager will ask you to talk through an incident lifecycle; they will not ask you to configure a dashboard.

---

## Repo structure

```
ServiceNow-ServiceDesk-Lab/
├── README.md                  ← you are here
├── 00-SETUP.md                ← account + PDI, plus fallbacks if the waitlist bites
├── labs/
│   ├── LAB-01-navigation-and-admin-basics.md
│   ├── LAB-02-incident-management.md
│   ├── LAB-03-service-catalog-and-requests.md
│   ├── LAB-04-knowledge-management.md
│   ├── LAB-05-change-and-problem.md
│   └── LAB-06-cmdb-sla-and-reporting.md
├── notes/
│   ├── GLOSSARY.md            ← tables, prefixes, states, jargon
│   ├── INTERVIEW-PREP.md      ← 25 questions with answers, plus CV bullets
│   └── RESOURCES.md           ← every official link, ranked
└── evidence/                  ← your screenshots go here
```

---

## How to use each lab file

Every lab follows the same pattern:

1. **Concept** — 5 lines on what the module is for and why the business cares.
2. **Steps** — numbered clicks. Navigation is written as `All → Incident → Create New`.
3. **Record it** — what to screenshot and what number to log.
4. **Interview angle** — the question a hiring manager actually asks about this module.

Fill in the `Result:` lines as you go. Those filled-in numbers are what make the repo look like real work rather than a copied tutorial.

---

## Publishing this to GitHub

```bash
cd ServiceNow-ServiceDesk-Lab
git init
git add .
git commit -m "ServiceNow service desk lab: 7-hour ITSM hands-on path"
git branch -M main
git remote add origin https://github.com/NoelJoseph-it-admin/ServiceNow-ServiceDesk-Lab.git
git push -u origin main
```

Create the empty repo on GitHub first (no README, no .gitignore — this repo already has one).

**Commit as you go, not all at the end.** One commit per lab block gives you a contribution graph that shows a real study session:

```bash
git add labs/LAB-02-incident-management.md evidence/
git commit -m "Lab 02: incident lifecycle end to end, INC0010045-0010052"
git push
```

---

## Screenshot discipline

Redact nothing except your instance URL if you'd rather not share it. Name files so they sort:

```
evidence/lab02-01-incident-form-new.png
evidence/lab02-02-priority-matrix.png
evidence/lab02-03-resolved-with-close-notes.png
```

Aim for 12–20 screenshots total across all labs. That is enough to be credible and few enough to actually take.

---

## What this does not make you

Completing this does not make you a ServiceNow administrator, and you should not claim to be one. It makes you a person who can walk into a service desk on day one and work a queue without hand-holding. On a CV, that is the line: *"Hands-on ServiceNow ITSM experience across incident, request, knowledge and change workflows in a personal developer instance."*

The natural next steps after this are ITIL 4 Foundation (the vocabulary employers assume you have) and, if you want to go deeper, the ServiceNow Certified System Administrator path. Both are covered in [notes/RESOURCES.md](notes/RESOURCES.md).
