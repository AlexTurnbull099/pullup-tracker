# Project Brief — Pull-Up Tracker App

A personal app to track my workouts against the plan in `pullup-summer-plan.md`. Read that file first — it's the source of truth for the program. This brief describes the app I want built around it.

## Goal
Keep me consistent on the bar from now through September, and show me that I'm actually progressing (more strict pull-ups, more total volume) over the 10 weeks.

## Core concept
The plan runs on a repeating cycle: **HEAVY → VOLUME → LIGHT → HEAVY → VOLUME → LIGHT → rest**. The app should know where I am in that cycle, tell me what today's session is, let me log it, and show my progress over time.

---

## v1 — must have

**1. Today's workout**
- Show what day-type is up next in the cycle (Heavy / Volume / Light / Rest).
- Display that day's exercise list pulled from the plan, each with its target sets × reps.
- Let me check off each exercise and enter what I actually did (sets and reps per set).
- A "Done" action that logs the session with today's date and advances the cycle.
- Let me override the day-type if I rest or rearrange (life happens).

**2. Session logging**
- Per session, store: date, day-type, each exercise with actual sets/reps, and a free-text note ("felt strong", "skipped last set", etc.).
- Optionally log bodyweight for the day (for tracking size gain — keep this optional and low-key, not the focus).

**3. Progress tracking**
- A **strict pull-up max** number I can update (the headline metric). The plan's Phase 2 goal is to roughly *double* my starting max, and Phase 3 ends with a new max test — surface progress toward that.
- A simple line chart of strict max over time.
- A simple chart of total pull-up/chin-up volume per week (sets × reps summed), so I can see volume climbing.

**4. Where am I in the plan**
- Show the current phase (Foundation wk 1–3 / Build wk 4–7 / Intensify wk 8–10) and the week number, counting from my start date.
- A one-line reminder of that phase's focus (text is in the plan).

**5. Consistency**
- A streak / sessions-this-week counter. Nothing punishing — just a nudge. Missing a day is fine; the plan wants at least one rest day a week anyway.

---

## Nice to have (only after v1 works)
- The progression rule from the plan baked in: when I hit the top of a rep range across all sets of an exercise, flag it and suggest leveling up (more reps → slower tempo → add weight).
- A backpack-weight field on exercises for Phase 3.
- A calendar/history view of past sessions.
- Export my log to CSV or JSON.

## Explicitly out of scope for v1
- Accounts, login, or any server/auth.
- Social features.
- Anything diet- or calorie-related beyond the optional bodyweight field.

---

## Tech notes (suggestions, your call)
- I want to **run this locally and easily** — a single-page app I can open in a browser is perfect. A standalone HTML file or a small React app both work.
- Persist data on-device (local storage or a local file is fine for a personal tool) — no backend needed.
- Keep the UI clean and fast to use mid-workout on a phone, since I'll be tapping between sets. Big tap targets, minimal typing.
- Let's start minimal and iterate — build v1, I'll try it for a session, and we'll refine from there.

## First step
Read `pullup-summer-plan.md`, confirm you understand the cycle and exercises, then scaffold v1. Ask me anything ambiguous before building.
