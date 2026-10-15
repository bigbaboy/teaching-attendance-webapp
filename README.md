# Teaching Attendance Web App
### Điểm danh suất dạy · Interactive portfolio demo

A responsive Vietnamese web interface for recording teaching sessions by teacher, date, location and subject.

## What you can try

- Browse a monthly calendar and select a teaching date.
- Choose a sample teacher, location and subject.
- Select one or more teaching slots and add a note.
- Create, update or delete a sample daily record.
- See monthly session totals, recorded days and the selected day's session count.

## Project context

The original application uses an HTML/CSS/JavaScript interface with Google Apps Script and Google Sheets. This repository publishes a **standalone demonstration adapted from that interface**.

| Version | Data layer | Persistence |
| --- | --- | --- |
| Original application | Google Apps Script / Google Sheets | Spreadsheet-backed |
| This public demo | JavaScript mock adapter with synthetic teachers | In-memory; resets on reload |

The demo contains no real teacher or student records, spreadsheet identifiers, credentials or production endpoints. It does not write to Google Sheets.

## Run locally

Open `index.html` in a modern browser. No dependencies or API keys are required.

For a local server:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`.

## Walkthrough

1. Choose **Giáo viên mẫu 01**.
2. Select a date with no existing record.
3. Pick a subject, location and one or more time slots.
4. Click **Lưu điểm danh** and inspect the calendar totals.
5. Change the selected slots and click **Cập nhật điểm danh**.
6. Try **Xóa**, or reload the page to restore the sample dataset.

## Design and implementation

- Responsive calendar and form layout for desktop and mobile.
- Form validation, save/update states and a deletion confirmation.
- Vietnamese date formatting and accessible form labels.
- A separate `callServer()` adapter lets the UI demonstrate the original request flow without a backend.
- Sample data is generated for the selected month.

## Scope

This repository currently includes the demo frontend, not the full production Apps Script backend. Authentication, concurrent edits and production persistence are outside the demo. Session totals here count selected time slots, not teaching hours.

**Author:** Lê Minh Đạt · [GitHub profile](https://github.com/bigbaboy)
