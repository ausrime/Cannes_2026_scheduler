# Cannes 2026 Schedule Planner

Interactive Gantt chart and schedule planner for the 78th Cannes Film Festival (May 12–23, 2026).

**Live site:** https://ausrime.github.io/Cannes_2026_scheduler/

## What it does

- **Daily Gantt** — venues on the Y axis, time on the X axis, sections distinguished by color. Pick a day to switch the view.
- **Filters & search** — section dropdown, venue dropdown (Le Cineum's four halls collapse into one), time window (with AM/PM/Eve presets), and a free-text search across title and director. Filter options reflect only what's actually scheduled on the selected day.
- **Overlap-safe layout** — screenings at the same venue with overlapping times stack into sub-rows so every film stays readable.
- **Midnight screenings on the right day** — films starting before 06:00 are shown under the *previous* calendar day, drawn past the 24:00 mark. The bar still shows the real ticket time (e.g., 00:30).
- **My Schedule** — tap the ★ on any film to bookmark it. The "My Schedule" tab shows your picks as a list (with conflict warnings when picks overlap) or as a personal Gantt. Picks persist via `localStorage`.
- **Mobile-friendly** — responsive layout, tap-to-pin tooltips, larger touch targets, single-column cards on small screens.

## Files

| File                    | Purpose                                                                |
|-------------------------|------------------------------------------------------------------------|
| `cannes_gantt.html`     | The app — self-contained HTML + CSS + JS in a single file.             |
| `cannes_schedule.csv`   | Schedule data. The app fetches this at runtime, with an embedded copy as fallback for `file://`. |
| `logo_2026.svg`         | Favicon.                                                               |
| `index.html`            | Redirects the bare URL to `cannes_gantt.html`.                         |

## Updating the schedule

Edit `cannes_schedule.csv` and push. The app refetches the file on each page load, so the live site picks up your edits without a rebuild.

CSV columns: `Date,Time,Location,Section,Film Title,Director,Duration` — duration in `1h45` form, empty for ceremonies (defaults to 90 min).

```
git add cannes_schedule.csv
git commit -m "Update schedule"
git push
```
