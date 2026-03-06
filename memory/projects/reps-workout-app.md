# Project: REPS Workout App

**Status:** Active development
**Platform:** Single-file PWA (`workout.html`)
**Owner:** Erik

## What It Is
A personal workout tracker that lives as a single `.html` file.
No server, no account, no install required. Open in mobile browser, save to home screen.
All data stored in `localStorage`. JSON export/import for backup and phone switching.

## Design Direction
- Reference: Nike Training Club
- Name: REPS (wordmark as outlined SVG paths, no font dependency)
- Accent: Lime `#C8FF00` on near-black `#0A0A0A` backgrounds
- Style: Bold, athletic, clean — no emoji, SVG icons only
- Set indicators: Filled/empty dots (not numbers)
- Most important screen: The logging screen (ExerciseCard during active workout)

## Features Built
- [x] 5-tab layout: Today, Program, Progress, Library, Settings
- [x] Weekly program builder (define exercises per day)
- [x] Workout logging — tap exercise → log sets one by one
- [x] Progressive overload suggestions (+2.5 kg when all reps hit)
- [x] Exercise swap by muscle group during workout
- [x] Manual rest timer
- [x] Per-exercise progress charts (max weight + volume over time)
- [x] Exercise library with muscle group filtering
- [x] JSON backup export / import (for phone switching)
- [x] Completed workout state on Today screen (summary + stats)
- [x] SVG icons throughout (no emoji)
- [x] Muscle group colour system (left border on cards + MgPill)
- [x] Seed data + importable mock JSON (8 weeks Push/Pull/Legs)
- [x] PWA — manifest.json, apple-touch-icon, no-cache headers, deployed on GitHub Pages (mrhos/reps)
- [x] Ring progress indicator on active workout header
- [x] Day strip (M T W T F S S) on Today screen
- [x] Pill filters on Progress charts tab
- [x] Celebratory completion screen (lime, stats summary)
- [x] Weekly backup nudge banner (dismissible, after 7 days)
- [x] Haptic feedback — navigator.vibrate(30) on every set logged
- [x] Workout duration timer — live MM:SS in active header; saved to log; shown on completion screen
- [x] Empty state illustrations — Progress, Program day, Library search (custom SVG)
- [x] Session history — Progress → History tab lists all sessions newest-first
- [x] Edit past workout — tap any session to view sets, edit weight/reps, add/remove sets
- [x] Delete workout — with confirmation; deleting today resets Today tab to Ready to Start

## Architecture Decisions
- **No build tools** — CDN React 18 + Babel standalone. Tradeoff: slower initial parse, but zero setup friction.
- **No chart library** — custom SVG LineChart component. Avoids CDN dependency risk.
- **localStorage only** — simple, offline-first, no auth needed for personal use.
- **Single file** — everything in workout.html. Easy to share, back up, inspect.
- **Bodyweight exercises** store athlete's bodyweight as `weight` field so volume and charts remain meaningful.

## Mock Data Split (rep-mock-data.json)
- **Push (Mondays):** Bench Press, OHP, Tricep Pushdown, Lateral Raises, Cable Fly
- **Pull (Wednesdays):** Pull-ups (BW=80kg), Barbell Row, Lat Pulldown, Bicep Curl, Face Pulls
- **Legs (Fridays):** Squat, Romanian Deadlift, Leg Press, Hip Thrust, Calf Raises
- 8 weeks, 24 sessions total, all showing clear progressive overload

## Known Quirks / Watch-outs
- Bodyweight exercises need a real `weight` value (bodyweight kg) — `weight: 0` breaks charts and volume
- `todayLog` detection uses ISO date match, not day name — so multiple sessions same day is supported
- `lastLog` in Ready-to-Start view excludes today's log (shows previous session, not today's)
- The chart requires at least 2 data points to render; shows "Log more sessions" placeholder otherwise
- `SEED_*` constants only apply on first load (empty localStorage); import JSON to override existing data
