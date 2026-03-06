# REPS — Project Memory

## Project
**REPS** is a single-file PWA workout tracker built for personal use.
No backend, no install — open in mobile browser and save to home screen.

## Key File
| File | What |
|------|------|
| `workout.html` | The entire app — all HTML, CSS, React/JSX in one file |
| `reps-mock-data.json` | Import via Settings to load 8 weeks of sample data |
| `TASKS.md` | Feature backlog |

## Tech Stack
| Thing | Detail |
|-------|--------|
| Framework | React 18 via CDN + Babel standalone (no build tools) |
| Storage | `localStorage` only — no backend |
| Charts | Custom SVG line chart (no external lib) |
| Platform | PWA — works as a home screen app on iOS/Android |

## Design Tokens (T object)
| Token | Value | Use |
|-------|-------|-----|
| `T.bg` | `#0A0A0A` | Page background |
| `T.card` | `#141414` | Card background |
| `T.card2` | `#1C1C1C` | Nested card / inputs |
| `T.lime` | `#C8FF00` | Primary accent (CTAs, active states) |
| `T.limeDim` | `rgba(200,255,0,0.12)` | Lime tint background |
| `T.red` | `#FF3B30` | Destructive actions |
| `T.dim` | `#777` | Secondary text |
| `T.border` | `#242424` | Card borders |

## Muscle Group Colours (MG object)
Chest=#FF6B6B · Back=#4FC4CF · Shoulders=#FFD93D · Biceps=#A29BFE · Triceps=#818CF8 · Quads=#F472B6 · Hamstrings=#FB923C · Glutes=#F97316 · Calves=#34D399 · Core=#60A5FA

## Data Structure
```
localStorage keys:
  wa_exercises   → array of { id, name, muscleGroup }
  wa_program     → { Monday: [{exerciseId, targetSets, targetReps}], ... }
  wa_logs        → array of { id, date (ISO), dayName, exercises: [{exerciseId, targetSets, targetReps, sets: [{weight, reps}]}] }
  wa_active      → active workout object (same shape as a log entry, no id/date yet)
  wa_last_backup → ISO timestamp of last export
```

## App Tabs
| Tab | Key | Icon | What |
|-----|-----|------|------|
| Today | `today` | Dumbbell | Start/log workout; shows completed state after saving |
| Program | `program` | Calendar | Define weekly split per day |
| Progress | `progress` | Chart | Per-exercise weight & volume charts |
| Library | `library` | List | Browse/add exercises by muscle group |
| Settings | `settings` | Gear | Export/import JSON backup, reset |

## Key Components
| Component | What |
|-----------|------|
| `SetDots` | Dot indicators — filled lime = done, grey = pending |
| `ExerciseCard` | Expandable card with inputs, set logging, rest timer, swap |
| `LineChart` | Custom SVG chart — takes `[{label, value}]` |
| `LimeBtn` | Primary CTA — lime bg, black text |
| `GhostBtn` | Secondary — transparent, dim border |
| `MgPill` | Coloured muscle group badge |
| `Wordmark` | "REPS" logo — inline outlined SVG, no font dependency |

## Key Helpers
| Helper | What |
|--------|------|
| `S.get/set` | localStorage wrapper with JSON parse/stringify |
| `getSuggestion(exerciseId, targetReps, logs)` | Returns progressive overload suggestion (+2.5kg if all reps hit) |
| `calcVolume(sets)` | Sum of weight×reps across sets |
| `todayName()` | Returns current day name e.g. "Monday" |
| `fmtDate(iso)` | Formats "2026-03-04" → "4 Mar" |

## Conventions
- All inline styles using the `T` design token object — no external CSS classes
- SVG icons all live in the `Icon` object at the top of the file
- Seed data: `SEED_EXERCISES`, `SEED_PROGRAM`, `SEED_LOGS` — used only when localStorage is empty
- Bodyweight exercises (e.g. Pull-ups) store athlete's bodyweight as `weight` so volume/charts work

→ Full project detail: memory/projects/reps-workout-app.md
