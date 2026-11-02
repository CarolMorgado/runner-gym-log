# Runner Gym Log

A mobile-first web app for following and logging a 4-week strength program for amateur runners. It works like a phone app from the home screen: tap through each session, log weights, tick off exercises, run rest timers, track body weight and send workouts to Strava.

**Live demo:** `https://<your-username>.github.io/runner-gym-log/`

---

## Why

Runners need strength work for legs and tendons, upper body, single-leg stability and power, but gym sessions have to fit around the weekly runs. Free gym apps limit how many routines you can save (around 3–4), while this program has 12 different workouts. Runner Gym Log holds the whole program and the logbook in one free page.

## Features

| Feature | What it does |
| --- | --- |
| 4-week program | 3 sessions per week (Day A, B, C) plus an optional Day D, with new exercise variations every week |
| Weight logging | Per-exercise kg input with −/+ buttons in 2.5 kg steps |
| "Last time" hint | Shows the weight from the previous log of that exercise |
| Progress bar | Tick off exercises and see how much of the session is done |
| Rest timer | One tap starts the right rest time; keeps the screen awake and vibrates when time is up |
| Form videos | Every exercise links to YouTube form videos |
| Warm-up & cool-down | Built-in mobility routines for every session |
| Body weight | Weekly entries with a trend chart |
| Strava export | Copy a workout summary for Strava, or download a `.fit` file that Strava imports as *Weight Training* |
| Training cycles | After Week 4, start a new cycle; previous weights stay visible as reference |
| Light & dark mode | Follows the phone's theme |

## Program

| Week | Focus | Load |
| --- | --- | --- |
| 1 — Foundation | Learn the movements | 3 × 10–12, moderate |
| 2 — Build | New variations, more volume | 3–4 × 8–10 |
| 3 — Strength & speed | Heavier, more plyometrics | 4 × 6–8 |
| 4 — Power & reset | Light weights moved fast, more mobility | Lower volume |

- **Day A:** legs, tendons and speed (plyometrics, calf/Achilles work, squats, hinges)
- **Day B:** back, chest and core
- **Day C:** single-leg stability, power and full body
- **Day D (optional):** mobility, core and foot strength

Every exercise, with sets, reps, rest and form cues, is in [docs/TRAINING-PLAN.md](docs/TRAINING-PLAN.md).

## Tech

- One `index.html` file: HTML, CSS and vanilla JavaScript, with no framework, no build step and no server
- Data saved in the browser (`localStorage`)
- Responsive, mobile-first layout with safe-area support for phones
- Google Fonts (Barlow, Barlow Condensed)
- Hand-written binary FIT encoder (Garmin's activity format, with CRC checksums), so a workout becomes a Strava upload without a server or API keys

## Use it

**Run locally:** download `index.html` and open it in a browser.

**Add to your phone's home screen:**
- iPhone (Safari): Share → *Add to Home Screen*
- Android (Chrome): ⋮ menu → *Add to Home screen*

**Log a workout to Strava:** at the bottom of a session, under **Log to Strava**, check the start time and minutes, then either:
- **Copy workout for Strava** → in the Strava app tap **+** → *Add manual activity* → Sport *Weight Training* → paste into the description, or
- **Download .fit file** → upload it at [strava.com/upload/select](https://www.strava.com/upload/select)

## How it was built

Built with an AI assistant (Claude) from a written list of requirements: 3 gym days a week around running, at most 90 minutes, fast pace, a 4-week rotation, sets, reps and form videos, and an easy logger to use at the gym.

| Step | Time |
| --- | --- |
| Requirements → full 4-week training plan | ~6 min |
| Plan → working tracker app | ~5 min |
| Strava export (follow-up) | ~10 min |

## Roadmap

- [x] Strava export (copy summary + `.fit` file)
- [ ] Export logs to CSV
- [ ] Per-exercise weight progress chart
- [ ] Offline install as a full PWA (manifest + service worker)

## Disclaimer

The training plan is general guidance for healthy adults, not medical advice. With an injury, check with a physiotherapist first.

## License

[MIT](LICENSE)
