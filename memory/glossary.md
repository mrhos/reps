# Glossary

## App Terms
| Term | Meaning |
|------|---------|
| REPS | The app name. Wordmark shown in the header as outlined SVG paths. |
| PWA | Progressive Web App — save workout.html to phone home screen, works offline |
| active workout | An in-progress session stored in `wa_active` localStorage key |
| log / session | A completed workout saved to `wa_logs` |
| program | The weekly split — which exercises to do each day of the week |
| progressive overload | Auto-suggestion: if all sets hit target reps, suggest +2.5 kg next session |
| seed data | Default data loaded into localStorage on first open (SEED_EXERCISES, SEED_PROGRAM, SEED_LOGS) |
| hot cache | CLAUDE.md — quick-reference memory for the most common project context |

## Design Terms
| Term | Meaning |
|------|---------|
| lime | The primary accent colour — `#C8FF00` |
| T object | Design token object at top of workout.html — all colours, spacing, etc. |
| MG object | Muscle group → colour mapping |
| SetDots | The filled/empty dot indicators showing set progress |
| MgPill | Small coloured badge showing muscle group (e.g. "Chest") |
| left border | 3px coloured left border on exercise cards keyed to muscle group |
| frosted nav | Bottom nav bar with `backdrop-filter: blur(20px)` |

## Data Keys
| Key | What's stored |
|-----|---------------|
| `wa_exercises` | Array of all exercises |
| `wa_program` | Weekly program split |
| `wa_logs` | All completed workout sessions |
| `wa_active` | Current in-progress workout (null when none) |
| `wa_last_backup` | ISO timestamp of last JSON export |

## Muscle Groups
Chest, Back, Shoulders, Biceps, Triceps, Quads, Hamstrings, Glutes, Calves, Core, Full Body
