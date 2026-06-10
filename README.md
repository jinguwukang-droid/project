# Trackary

A tiny, zero-dependency app for tracking anything — habits, expenses, workouts,
cups of coffee, whatever you want to count.

## Run it

Open `index.html` in a browser. That's it — no build step, no server, no
dependencies. (If you prefer serving it: `python3 -m http.server` and visit
http://localhost:8000.)

## Features

- **Trackers** — create as many as you like, each with a name, an optional
  unit (km, cups, $…), and a color.
- **Entries** — log a numeric value with an optional note; entries are
  timestamped automatically.
- **Stats** — per tracker: total entries, summed value, active days, and
  current day streak.
- **Chart** — a 14-day bar chart of daily totals (hover a bar for the value).
- **Persistence** — everything is saved to your browser's localStorage.
- **Export / Import** — download all data as JSON and restore it later or on
  another machine.

## Data

All data stays in your browser under the localStorage key `trackary.v1`:

```json
{
  "trackers": [{ "id": "...", "name": "Running", "unit": "km", "color": "#5b8cff", "createdAt": "..." }],
  "entries":  [{ "id": "...", "trackerId": "...", "value": 5, "note": "morning run", "at": "..." }]
}
```

The Export button produces this same structure, so exports are easy to inspect
or process with other tools.
