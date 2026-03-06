# REPS — Task Backlog

Tasks are grouped by theme. Move to **Done** when shipped.

---

## 🏋️ Logging & Workout UX

- [x] **Workout duration timer** — show elapsed time during active workout; save duration to log
- [ ] **Per-exercise notes** — small text field on ExerciseCard to jot form cues or how it felt
- [ ] **Bodyweight exercise flag** — mark exercise as bodyweight in Library; auto-fill athlete's BW as weight, show reps-only in logging UI
- [ ] **Superset support** — link two exercises to log them back-to-back with shared rest timer
- [ ] **Custom rest timer per exercise** — currently one global timer; let user set default per exercise in Library
- [ ] **Quick-log last session** — one-tap to pre-fill all sets with last session's weights/reps

---

## 📊 Progress & Stats

- [ ] **Personal records (PRs)** — detect and badge when a new max weight or volume is hit for an exercise
- [ ] **Workout streak** — count consecutive weeks with at least N sessions; show streak on Today screen
- [ ] **Total stats dashboard** — all-time totals: sessions, sets, volume, most-trained muscle group
- [ ] **Calendar heatmap** — visual grid of training days on the Progress tab (like GitHub contributions)
- [ ] **Volume chart improvement** — show actual kg numbers on Y-axis instead of implied scale
- [ ] **Multi-exercise comparison** — overlay two exercises on the same chart

---

## 📋 Program & Planning

- [ ] **Deload week** — option to schedule a reduced-weight week in the program
- [ ] **Rest day notes** — add an optional note to a rest day (e.g. "cardio", "mobility")
- [ ] **Program templates** — pre-built splits: PPL, Upper/Lower, Full Body 3x, Bro Split
- [ ] **Exercise order drag-to-reorder** — reorder exercises within a day in Program view

---

## 🎨 Design & Polish

- [x] **Haptic feedback** — light vibration on set logged (mobile web `navigator.vibrate`)
- [ ] **Animated set dots** — small pop/scale animation when a set dot fills in
- [ ] **Swipe to delete set** — swipe gesture on a logged set row to remove it
- [ ] **Loading/transition states** — subtle fade between tabs
- [x] **Empty state illustrations** — SVG spot illustrations for Library empty state, first-time Program setup

---

## ⚙️ Settings & Data

- [ ] **Athlete profile** — store name, bodyweight, units (kg/lbs) in Settings
- [ ] **kg / lbs toggle** — unit preference with auto-conversion throughout
- [x] **Auto-backup reminder** — nudge banner on Today screen after 7 days without export; dismissible, links to Settings
- [ ] **iCloud / Google Drive export** — native share sheet on iOS/Android for backup file
- [ ] **Edit past workout** — tap a session in Progress recent list to view and edit logged sets

---

## Done ✅

- [x] Weekly program builder
- [x] Workout logging (tap exercise → log sets)
- [x] Progressive overload suggestions (+2.5 kg)
- [x] Exercise swap by muscle group
- [x] Manual rest timer
- [x] Per-exercise progress charts (weight + volume)
- [x] Exercise library
- [x] JSON backup export / import
- [x] Completed workout state on Today screen
- [x] SVG icons throughout (no emoji)
- [x] Muscle group colour system
- [x] Importable mock data (8-week Push/Pull/Legs history)
- [x] CLAUDE.md project memory + TASKS.md backlog
