# Subscription Reminder Pro+

A powerful, privacy-friendly, single-file subscription and bill reminder app that runs entirely in the browser. It helps you track renewals, recurring payments, due dates, reminder schedules, payment history, upcoming costs, and calendar alerts without requiring a backend server or account system.

Subscription Reminder Pro+ is designed for personal finance tracking, subscription management, renewal planning, and lightweight bill organization.

---

## ✨ Features

### Core Subscription Tracking

- Add, edit, duplicate, and delete subscriptions
- Track subscription name, due date, amount, currency, notes, and tags
- Store payment method details such as card nickname or PayPal
- Add account or cancellation URLs for quick access
- Mark subscriptions as paid
- Automatically advance recurring subscriptions after payment
- Record payment history for each subscription
- Search by name, tag, note, category, or payment method

---

## 🔔 Smart Reminders

Subscription Reminder Pro+ supports multiple reminder times before each due date.

Built-in reminder presets include:

- 30 days before
- 7 days before
- 1 day before
- 6 hours before
- 1 hour before
- 15 minutes before

You can also add a custom reminder in minutes.

Notifications use the browser Notification API where supported. The app also includes an optional audio beep for on-page alerts.

> Important: Browser reminders work best while the page is open or recently active. For more reliable system-level reminders, export the subscription to your calendar using ICS or Google Calendar.

---

## 🔁 Recurring Payments

Supported recurrence types:

- None
- Weekly
- Monthly
- Quarterly
- Yearly
- Custom interval in days

Monthly recurrence is handled carefully so dates near the end of the month behave more sensibly. For example, a subscription due on the 31st will clamp to the last available day of shorter months.

---

## 📊 Dashboard and Insights

The dashboard gives a fast overview of your subscription load.

It includes:

- Total due in the next 30 days
- Monthly cost projection
- Overdue subscription count
- Active subscription count
- Upcoming renewal timeline
- Smart insights panel
- Largest active bill detection
- Next renewal summary
- Top category estimate
- Backup reminders

---

## 🏷️ Organization Tools

Subscriptions can be organized with:

- Tags
- Categories
- Priority levels
- Auto-pay status
- Payment method
- Notes
- Merchant/account URL

Priority levels include:

- Normal
- Watch closely
- Critical

Filters include:

- All
- Upcoming
- Soon / within 72 hours
- Overdue
- Completed
- Auto-pay
- Critical

Sort options include:

- Due soonest
- Due latest
- Amount high to low
- Amount low to high
- Name A–Z
- Recently added

---

## 📅 Calendar Integration

Each subscription can be exported to calendar tools.

Supported calendar actions:

- Download `.ics` calendar event
- Open a pre-filled Google Calendar event

ICS exports include:

- Subscription name
- Due date and time
- Amount
- Category
- Payment method
- Notes
- Account URL, if available
- Reminder alarms based on selected reminder presets

---

## 💾 Backup and Import

The app stores data locally in your browser using `localStorage`.

Backup options:

- Export full JSON backup
- Import JSON backup
- Export CSV for spreadsheet analysis
- Print a clean report view

JSON export preserves full app data, including:

- Subscriptions
- Reminder offsets
- Recurrence settings
- Notes
- Payment history
- Categories
- Tags
- Priority
- Auto-pay status

CSV export is useful for budgeting, reporting, and spreadsheet review.

---

## 🎨 Themes and Accessibility

Subscription Reminder Pro+ includes multiple display modes:

- Dark mode
- Light mode
- High contrast mode

Accessibility-focused features include:

- Keyboard-friendly controls
- Focus outlines
- Semantic labels
- Responsive layout
- Printable view
- Search shortcut
- Clear visual status badges

Keyboard shortcuts:

| Shortcut | Action |
|---|---|
| `/` | Focus search |
| `N` | Start a new subscription |
| `Esc` | Clear search field |

---

## 🧠 Local-First Privacy

This app does not require:

- A server
- A database
- A login system
- A cloud account
- External API keys

Your data stays in your browser unless you export it yourself.

Stored data includes:

- Subscription names
- Due dates
- Amounts
- Notes
- Tags
- Payment history
- Preferences

Because the app uses browser storage, clearing site data may delete your saved subscriptions. Regular JSON backups are recommended.

---

## 🚀 Getting Started

### Option 1: Run Locally

1. Save the file as:

```text
index.html
````

2. Open it in a modern browser.

Recommended browsers:

* Chrome
* Edge
* Firefox
* Safari

3. Add your first subscription.

---

### Option 2: Host as a Static Page

You can host the app on any static hosting service.

Examples:

* GitHub Pages
* Netlify
* Vercel
* Cloudflare Pages
* Local web server

No build step is required.

---

## 🧪 Demo Data

Click **Add Demo** to generate example subscriptions such as:

* Netflix
* Phone Bill
* Rent
* Gym
* Domain Renewal
* Cloud Backup

This is useful for testing the dashboard, filters, reminders, and export tools.

---

## 📖 How to Use

### Add a Subscription

1. Enter the subscription name.
2. Choose the due date and time.
3. Add the amount and currency.
4. Select reminder times.
5. Choose recurrence.
6. Add tags, category, payment method, and optional notes.
7. Click **Add Subscription**.

---

### Mark a Subscription as Paid

Click **Mark Paid** on a subscription card.

If the subscription is recurring, the app will:

1. Save a payment history entry.
2. Move the due date to the next billing cycle.
3. Reset reminder notifications for the next cycle.

If the subscription is not recurring, it will be marked as completed.

---

### Snooze a Subscription

Use:

* `+10m` to snooze by 10 minutes
* `+1d` to snooze by 1 day

Snoozing updates the due time and resets reminder flags.

---

### Export to Calendar

Use:

* **ICS** to download a calendar event file
* **GCal** to open Google Calendar with the event pre-filled

This is recommended for reminders that need to work even when the browser tab is closed.

---

### Backup Your Data

Use **Export JSON** to create a full backup.

Use **Import JSON** to restore or merge previous backups.

Use **Export CSV** for spreadsheet budgeting.

---

## 🛠️ Technical Details

Subscription Reminder Pro+ is built with:

* HTML
* CSS
* Vanilla JavaScript
* Browser Notification API
* Service Worker notification bridge
* localStorage
* BroadcastChannel for multi-tab syncing
* Blob-based export tools
* ICS calendar generation
* Google Calendar URL templates

No frameworks, build tools, or package managers are required.

---

## 📁 Data Model Overview

Each subscription stores information similar to:

```js
{
  id: "unique-id",
  name: "Netflix",
  dueISO: "2026-06-01T09:00:00.000Z",
  amount: 10.99,
  currency: "GBP",
  notes: "Standard plan",
  tags: ["streaming"],
  category: "Streaming",
  paymentMethod: "Visa ending 1234",
  merchantUrl: "https://example.com/account",
  priority: "normal",
  autoPay: false,
  muteSound: false,
  recurrence: {
    type: "monthly"
  },
  remindOffsets: [604800000, 86400000],
  completed: false,
  payments: []
}
```

---

## 🔐 Privacy and Security Notes

Subscription Reminder Pro+ is local-first, but users should still be careful with sensitive information.

Recommended practices:

* Avoid storing full card numbers
* Use nicknames such as `Visa ending 1234`
* Export JSON backups only to trusted storage
* Do not upload backups to public repositories
* Be careful when using shared computers
* Clear browser data if using a public device

The app does not encrypt localStorage data by default.

---

## ⚠️ Browser Reminder Limitations

Browser notifications have some limitations:

* Notifications may not work until permission is granted
* Some browsers restrict notifications from local files
* Reminders are most reliable while the app is open
* Long-term background notifications are not guaranteed
* Mobile browser behavior may vary

For important bills, use the ICS or Google Calendar export.

---

## 🧩 Current Feature Checklist

* [x] Add subscriptions
* [x] Edit subscriptions
* [x] Delete subscriptions
* [x] Duplicate subscriptions
* [x] Search subscriptions
* [x] Filter subscriptions
* [x] Sort subscriptions
* [x] Multiple reminders
* [x] Custom reminder timing
* [x] Browser notifications
* [x] Audio alerts
* [x] Silent reminder option
* [x] Weekly recurrence
* [x] Monthly recurrence
* [x] Quarterly recurrence
* [x] Yearly recurrence
* [x] Custom day recurrence
* [x] Payment history
* [x] Mark paid
* [x] Auto-advance recurring subscriptions
* [x] Snooze reminders
* [x] Tags
* [x] Categories
* [x] Priority levels
* [x] Auto-pay flag
* [x] Payment method field
* [x] Merchant/account URL field
* [x] Dashboard totals
* [x] Monthly projection
* [x] Upcoming timeline
* [x] Smart insights
* [x] JSON export
* [x] JSON import
* [x] CSV export
* [x] Print view
* [x] ICS export
* [x] Google Calendar link
* [x] Dark mode
* [x] Light mode
* [x] High contrast mode
* [x] Multi-tab sync
* [x] Demo data
* [x] Local-first storage

---

## 🗺️ Possible Future Improvements

Ideas for future versions:

* Optional encrypted backup files
* Password-protected local vault mode
* Budget limit warnings
* Spending charts
* Category pie chart
* Renewal heatmap calendar
* Browser install prompt
* Mobile-first compact mode
* Custom currencies
* Exchange-rate support
* Email reminder integration
* Push notification backend option
* Import from bank CSV files
* Subscription cancellation checklist
* Price increase tracking
* Renewal negotiation notes
* Shared household subscription mode

---

## 🧑‍💻 Development

Because the app is a single HTML file, development is simple.

Clone or download the project, then open:

```text
index.html
```

For a local server, you can use:

```bash
python -m http.server 8000
```

Then visit:

```text
http://localhost:8000
```

Using a local server may improve Service Worker and notification behavior compared with opening the file directly.

---

## 🧯 Troubleshooting

### Notifications do not appear

Check that:

* Browser notifications are supported
* Notification permission is granted
* The tab is open or recently active
* The browser is not blocking notifications
* Do Not Disturb / Focus mode is disabled

---

### My data disappeared

Possible causes:

* Browser site data was cleared
* The app was opened from a different origin or file path
* Private browsing mode was used
* Another browser profile was used

Restore your data using a JSON backup if available.

---

### Import failed

Make sure the imported file is:

* A valid JSON file
* Previously exported from this app
* Either an array of subscriptions or an object containing an `items` array

---

### Calendar reminders are not showing

After importing an ICS file, check your calendar app’s notification settings. Some calendar apps may ignore or modify imported alarm settings.

---

## 📄 License

This project can be released under the MIT License.

Example:

```text
MIT License

Copyright (c) 2026

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files, to deal in the Software
without restriction, including without limitation the rights to use, copy,
modify, merge, publish, distribute, sublicense, and/or sell copies of the
Software, subject to inclusion of the copyright notice and permission notice.
```

---

## 🙌 Credits

Built as a browser-based local-first subscription reminder and renewal management tool.

Created for users who want a simple but powerful way to track recurring costs, avoid surprise renewals, and keep subscription spending under control.

---

## Summary

Subscription Reminder Pro+ is a complete offline-friendly subscription manager with reminders, recurrence, calendar export, payment history, dashboard analytics, and backup tools. It keeps everything local, requires no backend, and works as a single HTML file.

```
```
