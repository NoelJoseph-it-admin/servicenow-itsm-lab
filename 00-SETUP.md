# Block 0 — Developer Account & Personal Developer Instance

**Time budget: 25 minutes.** Do this the night before if you can, because instance provisioning is the one step you don't control.

---

## 0.1 — Create a ServiceNow Developer account (5 min)

1. Go to **https://developer.servicenow.com**
2. Click **Sign up and Start Building** (top right).
3. Register with a personal email you check — a Gmail is fine, and often works better than a work address.
4. Verify via the confirmation link emailed to you.
5. Log back in and accept the Developer Program terms when prompted.

> Use the same email you use for ServiceNow University (Now Learning) later, so your achievements and your instance sit under one identity.

**Result:** Account created on `____/____/2026` with email `________________`

---

## 0.2 — Request your PDI (10 min, sometimes longer)

1. Signed in on the Developer Site, click **Request Instance** in the header.
2. Choose a release. Take the **latest available** unless it's waitlisted — as of mid-2026 the current release is **Australia**, with **Zurich** as the previous supported release. Either is completely fine for service desk learning; core ITSM barely changes between releases.
3. Click **Request**.
4. When provisioning finishes you'll get an "Your instance is ready!" dialog with three things. **Copy all three into a password manager immediately:**
   - Instance URL — `https://devXXXXXX.service-now.com`
   - Admin username — usually `admin`
   - Admin password
5. Click **Start Building** in the header to open the instance in a new tab.

**Result:**
- Instance: `dev____________.service-now.com`
- Release: `________________`
- Provisioned: `____/____/2026`

---

## 0.3 — If you get waitlisted (contingency)

PDI demand has repeatedly outstripped capacity through 2026, and there was an infrastructure incident in late July 2026 that took some instances offline and paused provisioning before being resolved. So have a plan B.

**If the request is waitlisted:**
- Try requesting an **older release** (e.g. Zurich instead of Australia). Waitlists are usually shorter on N-1.
- Check the Developer Site banner for any active incident before assuming your account is the problem.
- Meanwhile, **start Block 1 anyway** using ServiceNow's free on-demand courses, which include their own guided simulations — see [notes/RESOURCES.md](notes/RESOURCES.md). You lose the "my own instance" part but not the learning.

**Do not** pay a third party for a "ServiceNow instance." The PDI is free and it is the only legitimate free option.

---

## 0.4 — Protect your instance from reclamation (2 min)

This is the part most people miss and then lose a week of work.

Two rules that have applied since **11 July 2026**:

- **10-day rule:** log in *directly to the instance* at least once every 10 days. Logging into the developer *website* does not count. Background jobs do not count. Go to `https://devXXXXXX.service-now.com/login.do` and actually sign in.
- **90-day rule:** instances older than 90 days that also fail the activity check can be reclaimed. Reclamation resets the instance to factory state and reassigns it. There is no support and no recovery for free PDIs.

You will get advance notice by email before any reclamation. Read those emails.

**Mitigation:** everything valuable in this repo is markdown, not instance data. If you lose the PDI, you lose nothing that matters. That's by design.

**Set a calendar reminder now:** repeating every 7 days, "Log into ServiceNow PDI."

---

## 0.5 — First-login orientation (5 min)

Log in as `admin`. You'll land on either the classic UI or the Next Experience UI depending on release.

Do these four things immediately:

1. **Find your version.** In the filter/search box at the top of the left nav, type `stats.do` and press Enter. The page shows your build name and release. Screenshot it — it dates your work.
2. **Turn on the "All" menu.** In Next Experience, the left-hand **All** button opens the full application navigator. This is the single most important control in the product. Everything in these labs is written as paths from it.
3. **Star a favourite.** Navigate to `All → Incident → All`, then click the ☆ next to it in the nav. Favourites live under the bookmark icon.
4. **Find impersonation.** Click your avatar (top right) → **Impersonate User**. Confirm you can see it. You'll use this constantly.

**Screenshot for evidence:** `evidence/lab00-01-stats-do.png`

---

## 0.6 — Load demo data (optional, 3 min)

Most PDIs ship with the standard demo dataset already — users like Abel Tuter, Beth Anglin, and Fred Luddy, plus sample incidents and CIs. Check by going to `All → User Administration → Users` and searching for `Abel Tuter`.

If your instance is empty, that's unusual but not fatal — Lab 01 has you create your own users anyway.

---

## Checkpoint before moving on

- [ ] I can log into my PDI at `/login.do`
- [ ] I've saved the URL, username and password somewhere permanent
- [ ] I know my release name
- [ ] I've set a 7-day recurring reminder to log in
- [ ] I can find the **All** menu and the **Impersonate User** option

→ Continue to [LAB-01](labs/LAB-01-navigation-and-admin-basics.md)
