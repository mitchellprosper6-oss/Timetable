# Command Center

Block-based weekly timetable, focus timer, and manual time log. Runs offline as an installable app on your phone.

## Put it on your phone (GitHub Pages)

1. Create a new GitHub repository — call it `command-center`. Set it to **Public** (Pages needs public on free accounts).
2. Upload all five files to the root of the repo:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icon-192.png`
   - `icon-512.png`
3. In the repo, go to **Settings → Pages**. Under *Build and deployment*, set **Source: Deploy from a branch**, **Branch: `main`**, folder **`/ (root)`**. Save.
4. Wait about a minute, then open `https://YOUR-USERNAME.github.io/command-center/` on your phone.
5. Install it:
   - **iPhone (Safari):** Share button → *Add to Home Screen*. It must be Safari — Chrome on iOS can't install.
   - **Android (Chrome):** tap the **＋ Install app** button in the page, or the menu → *Install app*.

It now opens fullscreen with no browser bars, works with no signal, and keeps its own data.

## Updating it later

Replace the file in the repo, then **bump the cache name** in `sw.js` (`cc-v3` → `cc-v4`) so phones pick up the new version instead of the cached one. Close and reopen the app twice.

## Notes

- **Data lives on the device.** Each phone/browser keeps its own schedule and logged time — nothing syncs between them. Clearing site data wipes it.
- `index.html` also works on its own: download it and open it directly on a laptop, no server needed. You just don't get the installable-app behaviour that way.

## The three pages

**Schedule** — the week in blocks. Tap a day to switch. Tap a block to edit its time, name, skill tag, or type; **＋ Add block** for new ones. Each block has ○ to tick it done and ▶ to start a focus session on that skill.

**Focus** — pick a skill, pick 25/50/90 minutes (or a 5/10 break), Start. Completing a session logs it automatically. *Log & end* banks the time you've done so far. The bars at the bottom show logged vs planned per skill this week — the dashed mark is the plan, the solid bar is reality.

**Log** — for time you spent away from the timer. Pick the skill, tap a quick amount or type the minutes, set the date, add a note, done. Entries show whether they came from the timer or were added by hand, and feed the same weekly totals.

## The default week

One main subject a day — no more splitting focus across three or four topics. The plan repeats on a **2-week cycle** (Week A / Week B, shown and swappable at the top of the Schedule tab) so Python, C, C++ and ML/Maths all get fair rotation without cramming everything into one week. There are no idle gaps: every stretch of the day that isn't gym, a meal, drawing, or a Design/Git add-on is filled with that day's main subject, right up to 20:00.

| | |
|---|---|
| Day starts | 06:00, every day |
| Gym / run | 06:00–08:00 — Mon, Tue, Wed, Fri, Sat (unchanged) |
| Main subject | fills the rest of the day around gym/meals/drawing/add-on — one subject only, alternates by week |
| Add-on (Design / Git) | 15:15–16:15, only on Tue/Fri (Design) and Wed/Sat (Git) — minor, supplementary, same every week |
| Drawing | 16:15–17:15, **every day, same time**, towards the evening |
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
| C | ~13.0 |
| Python | ~12.0 |
| C++ | ~11.6 |
| ML / Maths | ~10.6 |
| Drawing | 7.00 |
| Design | 2.00 |
| Git | 2.00 |
| **Total** | **~58.25** |

Gym-day totals run to 6.75–8.5 hours of main subject on top of the gym session; Thursday and Sunday (no gym) run the longest at 8.75 hours main subject each, filling the day end-to-end. Comp Sci has been removed entirely, and C / C++ are now tracked as separate subjects. Design and Git are add-ons only — small, late-in-the-day blocks, not full study sessions. Every block is editable (and can be set to "Every week", "Week A only", or "Week B only"), so trim it to what you can actually hold — this is a fully-packed template, not a minimum.
