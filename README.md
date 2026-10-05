# Timetable

Block-based weekly timetable, focus timer, and manual time log. Runs offline as an installable app on your phone.

## Put it on your phone (GitHub Pages)

1. Create a new GitHub repository — call it `Timetable`. Set it to **Public** (Pages needs public on free accounts).
2. Upload all five files to the root of the repo:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icon-192.png`
   - `icon-512.png`
3. In the repo, go to **Settings → Pages**. Under *Build and deployment*, set **Source: Deploy from a branch**, **Branch: `main`**, folder **`/ (root)`**. Save.
4. Wait about a minute, then open `https://YOUR-USERNAME.github.io/Timetable/` on your phone.
5. Install it:
   - **iPhone (Safari):** Share button → *Add to Home Screen*. It must be Safari — Chrome on iOS can't install.
   - **Android (Chrome):** tap the **＋ Install app** button in the page, or the menu → *Install app*.

It now opens fullscreen with no browser bars, works with no signal, and keeps its own data.

## Updating it later

Replace the file in the repo, then **bump the cache name** in `sw.js` (`timetable-v8` → `timetable-v9`) so phones pick up the new version instead of the cached one. Close and reopen the app twice.

## Notes

- **Data lives on the device.** Each phone/browser keeps its own schedule and logged time — nothing syncs between them. Clearing site data wipes it.
- `index.html` also works on its own: download it and open it directly on a laptop, no server needed. You just don't get the installable-app behaviour that way.

## The three pages

**Schedule** — the week in blocks. Tap a day to switch. Monday to Friday also have a **Uni day / Work day** selector. A work day replaces the whole uni day with a 07:50–15:30 shift (commute either side), keeps drawing at 16:30, adds a one-hour uni catch-up at 19:10 and keeps stretching at 22:10. Timetabled classes show in red with their room. Tap a normal block to edit its time, name, room, skill tag, type or week; **＋ Add block** adds a new one. Each block has ○ to tick it done and ▶ to start a focus session on that skill. One-off dates (deadlines, the mid-term, reading week) show as a note above the day.

**Focus** — pick a skill, pick 25/50/90 minutes (or a 5/10 break), Start. Completing a session logs it automatically. *Log & end* banks the time you've done so far. The bars at the bottom show logged vs planned per skill this week — the dashed mark is the plan, the solid bar is reality.

**Log** — for time you spent away from the timer. Pick the skill, tap a quick amount or type the minutes, set the date, add a note, done. Entries show whether they came from the timer or were added by hand, and feed the same weekly totals.

## The default week (Semester A 2026/27)

Built around the QMplus timetable for BEng DICE Year 1, which **repeats every 2 weeks** (Week A / Week B, shown and swappable at the top of the Schedule tab). Week A is the week starting Mon 5 Oct 2026.

| | Every week | Week A only | Week B only |
|---|---|---|---|
| Mon | EMS412U 12:00–14:00 (Great Hall) · EMS403U Studio 15:00–17:00 (Eng 1.12) | | |
| Tue | EMS430U 09:00–10:00 (Bancroft 1.15) · EMS412U 12:00–13:00 (David Sizer LT) · EMS403U 14:00–16:00 · EMS402U 16:00–18:00 (Bancroft 1.15A) | EMS402U 11:00–12:00 (Engineering 209) | campus study at 11:00 |
| Wed | EMS402U SEMS lecture 13:00–15:00 (iQ East Court 0.14) | | |
| Thu | EMS412U 14:00–15:00 (room TBC) | | EMS402U Maker Space 09:00–13:00 (from 29 Oct) |
| Fri | EMS412U 13:00–14:00 (Bancroft 1.15A) | | |

Around the classes:

| | |
|---|---|
| Wake / bed | 06:30 / 22:30 (weekends 07:30; Saturday bed 23:00) |
| Uni self-study | Mornings at home, with a set module per day (~21 h/week incl. weekend catch-up) |
| Drawing | 2 h every day — evenings on Mon/Tue, afternoons Wed–Fri, mornings at weekends |
| Gym | Mon 07:20, Wed 17:40, Fri 16:40, Sat 08:30 (90 min incl. travel) |
| Stretching | Every night, right before bed |
| Secondary learning | Phase 1: Python (Mon, Wed, Sat build) and ML / Maths (Thu, Fri, Sun) · Git in the Sunday weekly review · none on Tuesdays (9–6 on campus) |

Week 7 (2–6 Nov) has no timetabled teaching: the app shows a note on those days, but the class blocks stay in place, so ignore them that week. Every block is editable, so adjust it when QMplus changes.

Updating from an older version keeps your logged time but replaces the schedule with this default week (old block ticks are cleared).
