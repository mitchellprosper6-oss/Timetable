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

| | |
|---|---|
| Day starts | 06:00, every day |
| Gym / run | 06:00–08:00 — Mon, Tue, Wed, Fri, Sat |
| Meals | Breakfast, lunch, dinner — built in as breaks |
| Drawing | Every single day |
| Chill / stretch / extra | 18:30–20:00, every day |

Weekly split:

| Skill | Hours |
|---|---|
| C / C++ | 10.00 |
| Python | 10.00 |
| Drawing | 7.25 |
| Comp Sci | 6.00 |
| ML / Maths | 5.50 |
| Design | 5.50 |
| Git | 1.00 |
| **Total** | **45.25** |

Thursday runs longest at 8.25 hours since there's no gym; Sunday is the light day at 4.5. Every block is editable, so trim it to what you can actually hold.
