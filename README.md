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

Replace the file in the repo, then **bump the cache name** in `sw.js` (`timetable-v7` → `timetable-v8`) so phones pick up the new version instead of the cached one. Close and reopen the app twice.

## Notes

- **Data lives on the device.** Each phone/browser keeps its own schedule and logged time — nothing syncs between them. Clearing site data wipes it.
- `index.html` also works on its own: download it and open it directly on a laptop, no server needed. You just don't get the installable-app behaviour that way.

## The three pages

**Schedule** — the week in blocks. Tap a day to switch. Monday to Friday also have a **Study day / Work day** selector. A work day runs from 06:00–15:30, leaves 15:30–16:30 for travel/reset, and moves the two-hour gym block to 16:30; drawing is skipped on work days. Dinner and the evening routine follow with their existing durations. Saturday and Sunday each gain an extra one-hour morning drawing block. Tap a normal block to edit its time, name, skill tag, or type; **＋ Add block** adds a new one. Each block has ○ to tick it done and ▶ to start a focus session on that skill.

**Focus** — pick a skill, pick 25/50/90 minutes (or a 5/10 break), Start. Completing a session logs it automatically. *Log & end* banks the time you've done so far. The bars at the bottom show logged vs planned per skill this week — the dashed mark is the plan, the solid bar is reality.

**Log** — for time you spent away from the timer. Pick the skill, tap a quick amount or type the minutes, set the date, add a note, done. Entries show whether they came from the timer or were added by hand, and feed the same weekly totals.

## The default week

One main subject a day — no more splitting focus across three or four topics. The plan repeats on a **2-week cycle** (Week A / Week B, shown and swappable at the top of the Schedule tab) so Python, C, C++ and ML/Maths all get fair rotation without cramming everything into one week. There are no idle gaps: every stretch of the day that isn't gym, a meal, drawing, or a Design/Git add-on is filled with that day's main subject, right up to 20:00.

For Monday–Friday, switching the selected day to **Work day** changes only that day. The timetable recalculates instantly, and the Focus page's weekly planned totals update to match the available study time. Switching back restores the normal two-week plan. Work runs 06:00–15:30, travel/reset is 15:30–16:30, gym is 16:30–18:30, dinner is 18:30–19:30, and chill/stretch/extra is 19:30–21:00. Drawing is skipped on work days and bedtime is not changed. To add weekend drawing time without moving the rest of the day, Saturday uses 08:45–09:45 and Sunday uses 08:00–09:00 for morning drawing, replacing one hour of morning study on each day.

| | |
|---|---|
| Day starts | 06:00, every day |
| Gym / run | 06:00–08:00 — Mon, Tue, Wed, Fri, Sat (unchanged) |
| Main subject | fills the rest of the day around gym/meals/drawing/add-on — one subject only, alternates by week |
| Add-on (Design / Git) | 15:15–16:15, only on Tue/Fri (Design) and Wed/Sat (Git) — minor, supplementary, same every week |
| Drawing | Normal days: 16:15–17:15. Saturday adds 08:45–09:45; Sunday adds 08:00–09:00. Skipped on selected work days |
| Meals | Breakfast, lunch, dinner — built in as breaks, times unchanged |
| Chill / stretch / extra | 18:30–20:00, every day (unchanged) |

Main-subject rotation (repeats every 2 weeks):

| Day | Week A | Week B |
|---|---|---|
| Mon | Python | ML / Maths |
| Tue | C | Python |
| Wed | C++ | C |
| Thu | ML / Maths | C++ |
| Fri | Python | ML / Maths |
| Sat | C | Python |
| Sun | C++ | C |

Weekly split (approx., averaged across the 2-week cycle):

| Skill | Hours/week |
|---|---|
| C | ~12.0 |
| Python | ~11.5 |
| C++ | ~11.1 |
| ML / Maths | ~10.6 |
| Drawing | 9.00 |
| Design | 2.00 |
| Git | 2.00 |
| **Total** | **~58.25 (with no work days selected)** |

Gym-day totals run to 5.75–8.5 hours of main subject on top of the gym session; Thursday (no gym) runs the longest at 8.75 hours of main subject, while Sunday now uses one morning study hour for drawing. Comp Sci has been removed entirely, and C / C++ are now tracked as separate subjects. Design and Git are add-ons only — small, late-in-the-day blocks, not full study sessions. Every normal block is editable (and can be set to "Every week", "Week A only", or "Week B only"), so trim it to what you can actually hold — this is a fully-packed template, not a minimum.
