# Cannes 2026 Schedule Planner

Interactive Gantt chart and schedule planner for the 78th Cannes Film Festival (May 12–23, 2026).

**Live site:** https://ausrime.github.io/Cannes_2026_scheduler/cannes_gantt.html

## What it does

- **Daily Gantt** of every screening — venues on the Y axis, time on the X axis, sections distinguished by color.
- **Filters:** sections, venues (Le Cineum's four halls collapse into one), time window, and free-text search by title or director.
- **Overlap-safe layout:** screenings at the same venue with overlapping times stack into sub-rows.
- **My Schedule:** click ★ on any film to add it to a personal pick list. Persisted in `localStorage`. Per-day list view shows conflicts; gantt view shows your picks on the same grid.

## Files

| File                    | Purpose                                                              |
|-------------------------|----------------------------------------------------------------------|
| `cannes_gantt.html`     | Self-contained app (HTML + CSS + JS in one file)                     |
| `cannes_schedule.csv`   | Schedule data — edit this, the app reloads it on the next page load. |
| `logo_2026.svg`         | Favicon                                                              |

## Updating the schedule

Edit `cannes_schedule.csv` and push. The app fetches the file at runtime, so the live site picks up your edits on the next page load — no rebuild needed.

CSV columns: `Date,Time,Location,Section,Film Title,Director,Duration` (duration in `1h45` form).
