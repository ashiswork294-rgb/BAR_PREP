# BARPREP — Personal Bar Exam Preparation Workspace

A runnable, responsive, local-first study management web app built to the supplied BARPREP brief. It uses plain HTML, CSS, and JavaScript as a dependency-free alternative to Next.js, so it runs without API keys, a database account, or a build step.

## Run locally

1. Extract the ZIP (if downloaded).
2. Open `index.html` in a modern browser. For best results, use a local static server:
   - Python: `python3 -m http.server 8000`
   - Then open `http://localhost:8000`
3. Data is saved in the browser's `localStorage` under `barprep_data_v1`.

## Included

- Home dashboard with live daily study time, configurable exam countdown, October–December 2026 calendar, mission/revision summaries.
- Pomodoro (25/50 minutes), custom countdown, and stopwatch. Timestamp-based elapsed timing, pause/resume, refresh persistence, session recording split by local date, and optional completion bell.
- Daily Mission tasks with descriptions, subject, priority, assigned date, optional syllabus/case links, edit/delete, and completion history.
- Automatic +3-day and +10-day revisions. Missed items keep their original due date; completion is independent of the original task.
- Paper 1's 31 supplied topics and Paper 2's 15 supplied cases/decision numbers, persistent coverage checkboxes, and notes.
- Analytics from recorded timer sessions, 7/30-day and all-history ranges, daily average including zero-study days, productive day, studied-day count, and current streak.
- Settings, full JSON backup/restore, history clearing, and full reset.

## Data and privacy

This version is local-only and does not upload data to a server. Clearing browser storage can remove the workspace, so export a backup regularly. Restoring a backup replaces current local data. The supplied exam date defaults to 12 December 2026; the calendar intentionally remains limited to October, November, and December 2026.

## Known scope notes

- This is a self-contained local-first implementation, not a Supabase-backed multi-device app. Authentication and cloud sync are not configured.
- The interface uses a Google Fonts import for DM Sans and Noto Sans Devanagari, with system fallbacks if offline.
- Automated test files and framework-level unit tests are not included in this no-build version; date arithmetic, revision scheduling, and timer accounting are implemented directly in the app.
- Timer accounting is timestamp-based and records intervals when paused, completed, cleared, or the page is closed. A browser cannot guarantee execution while the device itself is powered off; on return, only the elapsed running interval is reconciled.

## Main file

`index.html` contains the full application source code.


## Personalization update
This version adds profile naming (default: ASHIS), five workspace themes (Classic ivory, Midnight navy, Sage calm, Rose study, Lavender focus), five accent colours, adjustable text size, compact layout, and selectable timer sounds with volume control and a preview button. These preferences are saved in the same browser's local storage and included in JSON backups.

## Updating an existing GitHub Pages site
1. Download the updated `BARPREP.zip` and extract it.
2. Open your GitHub repository and open the existing `index.html`.
3. Use the pencil/Edit button, or choose **Add file → Upload files** and upload the new `index.html` to the repository root, replacing the old version.
4. Commit the change. Refresh your published site. If the old version still appears, hard-refresh the browser.
5. Your existing study data is stored in that browser's local storage and should remain, but export a backup from Settings before updating as a precaution.
