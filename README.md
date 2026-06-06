# 🔥 Belly Fat Loss Tracker

A personal fitness dashboard built as a single HTML file. No backend, no framework, no dependencies — just drop it on GitHub Pages and it works.

**Live demo:** `https://mehedi-hasan4.github.io/fitness_tracker/`

---

## Features

| Section | What it does |
|---|---|
| **Daily Habits** | 6 tasks — fasting, steps, workout, water, no sugar drinks, no late eating |
| **Auto Monthly Grid** | Completing all 6 tasks auto-marks that day ✅ on the calendar |
| **Fasting Schedule** | Live clock showing current phase, countdown to next, row highlight |
| **BMI Calculator** | Enter height once — auto-updates every time you log weight |
| **Water Intake** | Tap cups (250ml each), choose 2L / 2.5L / 3L target, resets at midnight |
| **Step Counter** | Log daily steps, tracks 7-day history, 6,000 step goal |
| **Sleep Tracker** | Log bedtime + wake time, overnight math, quality rating (Good/Okay/Poor) |
| **Mood & Energy** | Daily energy level + hunger level + free text note |
| **Balanced Food Guide** | Reference list for allowed foods with portion rules |
| **Weekly Flex Food Log** | Track controlled cheat meals, resets every Sunday |
| **Weight Log** | Log weight in kg, shows ▼/▲ diff between entries |
| **Weekly Summary** | Auto-generated card — full days, step days, sleep nights, weight trend, smart tip |
| **Monthly Tracker** | GitHub-style calendar — past days manually toggleable, future locked |

---

## Smart Behaviours

- **Daily tasks auto-reset** at midnight (new day = fresh start)
- **Flex foods auto-reset** every Sunday midnight
- **Water resets** every midnight
- **All data persists** in `localStorage` — no account needed
- **BMI recalculates** instantly when new weight is logged
- **Weekly Summary updates** whenever tasks, steps, sleep or weight changes

---

## Deploy to GitHub Pages

```bash
# 1. Create a new repo on github.com (e.g. belly-fat-tracker)

# 2. Clone it
git clone https://github.com/yourusername/belly-fat-tracker.git
cd belly-fat-tracker

# 3. Copy the file
cp /path/to/fitness-tracker.html index.html
cp /path/to/README.md README.md

# 4. Push
git add .
git commit -m "Initial release"
git push origin main
```

Then go to **Settings → Pages → Branch: main → / (root) → Save**

Your tracker will be live at `https://yourusername.github.io/belly-fat-tracker/` within ~60 seconds.

---

## Local Use

Just open `index.html` in any browser. No server needed.

---

## Data Storage

All data lives in your browser's `localStorage`. It never leaves your device. Clearing browser data or using Private/Incognito mode will reset everything.

**Storage keys used:**

| Key | Content |
|---|---|
| `dailyTasks` | Today's task states (array of booleans) |
| `lastTaskDate` | ISO date of last task save |
| `flexFoods` | This week's flex food states |
| `lastFlexWeek` | ISO week key for flex reset |
| `monthProgress_YYYY-MM` | Completed days per month |
| `waterToday` | Cup count today |
| `waterDate` | ISO date for water reset |
| `waterTarget` | Cup target (8/10/12) |
| `stepsLog` | Array of `{date, steps, label}` |
| `sleepLog` | Array of `{date, bed, wake, hrs, quality}` |
| `moodLog` | Array of `{date, energy, hunger, note}` |
| `weights` | Array of `{weight, date, iso}` |
| `userHeight` | Height in cm (permanent) |

---

## Customisation

Open `index.html` and edit the data arrays at the top of the `<script>` block:

```js
// Change your daily tasks
const DAILY_TASKS = [
  { label:'16 Hour Fasting', desc:'Eat window e.g. 12pm – 8pm' },
  // ...
];

// Change your step goal
const STEP_GOAL = 6000;

// Change fasting schedule times
const FASTING_SCHEDULE = [
  { time:'07:00', label:'⏳ Fasting', ... },
  // ...
];
```

---

*Built with vanilla HTML, CSS, and JavaScript. Zero dependencies.*
