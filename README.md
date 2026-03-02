# Habit Planner Dashboard

A responsive, browser-based habit tracker with **Daily**, **Weekly**, and **Monthly** views.

It supports:
- checkbox habits
- target-goal (count) habits
- custom scheduling (daily, weekdays, weekly with multiple selected days)
- per-habit time reminders via browser notifications
- JSON export/import

All data is stored locally in your browser using `localStorage`.

## Features

- **Multi-view tracking**
  - **Daily Board**: focus on one day
  - **Weekly Table**: row-wise habits, day-wise columns
  - **Monthly Heatmap**: visual completion intensity by date

- **Habit types**
  - **Checkbox**: 0% or 100%
  - **Target Goal**: completion based on `value / target`

- **Scheduling**
  - Daily
  - Weekdays (Mon-Fri)
  - Weekly on selected days (e.g. Mon + Fri)

- **Progress**
  - Daily summary progress
  - Weekly per-habit progress bars
  - Monthly per-habit progress + heatmap

- **Notifications (Chrome and other modern browsers)**
  - Time-based reminders for scheduled habits
  - One reminder per habit per day (if not completed)

- **Data portability**
  - Export to JSON
  - Import from JSON export file

## Tech Stack

- HTML
- CSS
- Vanilla JavaScript (no framework, no build tools)
- Browser `localStorage` + Notifications API

## Run Locally

No dependencies required.

1. Clone/download the project.
2. Open `index.html` in your browser.

Optional: use a local static server if you prefer:

```bash
# Python 3
python -m http.server 8000
```

Then open `http://localhost:8000`.

## Usage

1. Create a habit:
   - name
   - type (Checkbox or Target Goal)
   - frequency
   - time
2. Track progress in Daily / Weekly / Monthly tabs.
3. Use **Import JSON** / **Export JSON** from the top action bar.
4. Click **Enable Notifications** to allow reminder notifications.

## Data Storage

Local keys used:

- `habitTracker.weekly.v1` → habits + entries
- `habitTracker.notifications.v1` → notification sent flags

Nothing is sent to a backend server.

## JSON Import/Export

Export format:

```json
{
  "version": 1,
  "exportedAt": "2026-03-02T12:00:00.000Z",
  "habits": []
}
```

Import accepts:
- exported object format above (`{ habits: [...] }`)
- direct habits array (`[...]`)

## Notifications Notes

- Notifications work when browser permission is granted.
- Reminder checks run in-page every minute.
- If the page is closed, reminders stop (no background service worker).

## Responsive Design

The interface is optimized for:
- desktop
- tablet
- mobile

Layouts, controls, and grids adapt across breakpoints for touch and smaller screens.

## License

MIT (you can replace this with your preferred license).

