# Cozy Shelter · Reminder Studio

A single-file, browser-only tool that reads a contacts CSV export and surfaces upcoming birthdays and anniversaries with a ready-to-copy message. It never sends anything for you — you copy the draft and send it yourself, from whichever app you already use.

**[Download `Cozy_Shelter_Reminder_Studio_v0.1.3.html`](Cozy_Shelter_Reminder_Studio_v0.1.3.html)** and open it in any modern browser (Chrome, Edge, Firefox). No install, no build step.

## Features

- **CSV import with column mapping** — works with any contacts export (Google Contacts, Outlook, phone-native exports); you tell it which column is the name, birthday, anniversary, relationship, or free-text notes, instead of guessing a fixed schema
- **Notes scanning** — if you map a column to "Notes", it looks for sentences containing birthday/anniversary keywords and pulls a date out of them, then shows every guess for you to confirm, edit, or skip before anything is added
- **Manual add/edit/delete** — works with zero imports too; add people directly in the dashboard
- **Custom relationships** — type anything (선생님, 거래처, 동호회...) instead of being limited to the 5 built-in categories; previously-used ones become autocomplete suggestions, and messages fall back to the "other" tone when a custom relationship doesn't match a built-in one
- **Lunar (음력) birthdays** — mark a birthday as lunar-calendar and it recomputes the correct solar date every year (1900–2050), leap months included; anniversaries stay solar-only for now
- **Upcoming dashboard** — sorted by how soon each date is, with today's and soon-due (configurable lead time) items highlighted, searchable by name, filterable by time range, sortable by date/name/relationship
- **Duplicate detection on import** — re-importing someone already on your list gets flagged, with an option to skip, add anyway, or merge (fills in a missing birth year without touching anything else)
- **"Done for today"** — dismiss the urgent highlight on a birthday/anniversary once you've handled it, without losing the entry
- **Milestone birthdays & anniversaries** — when a year is entered, milestone birthdays (1st/Dol, 60th/Hwangap, 70th, 80th) and round-number anniversaries (10/20/25/30/40/50 years) get a gold badge and are worked into the message text automatically
- **Backup export/import (JSON)** — save all your entries and settings (never your API key) to a file, and restore them on this browser or a new one
- **Message drafts** — a small template bank by relationship × occasion (Korean/English), with a shuffle button and one-click copy — sending stays manual, on purpose
- **Optional AI personalization (BYOK)** — bring your own Claude, OpenAI, Gemini, or Grok API key to get a freshly generated message each time instead of the fixed templates; off by default
- **Korean / English** UI toggle, color-vision-safe / high-contrast display modes

## Daily automatic check (optional)

This is a static file — it only runs when a browser tab has it open, and it always computes "today" from your system clock at that moment, so opening it manually any time works fine. If you'd like it to check itself every morning without you remembering, use whichever method matches your OS. (These same instructions are also built into the app's own **? Guide**, so they're available even if you only downloaded the `.html` file on its own.)

### Windows

1. Open **Task Scheduler** → **Create Basic Task…**
2. Name it (e.g. "Cozy Shelter Reminder Studio"), trigger **Daily**, pick a time (e.g. 08:00)
3. Action: **Start a program**, browse to your browser's `.exe`, and add the full path to this HTML file as an argument

Or from a terminal (adjust both paths first):

```bash
schtasks /create /tn "CozyShelterReminderStudio" /tr "\"C:\Program Files\Google\Chrome\Application\chrome.exe\" \"C:\path\to\Cozy_Shelter_Reminder_Studio.html\"" /sc daily /st 08:00
```

Delete the task any time with `schtasks /delete /tn "CozyShelterReminderStudio"`.

### macOS

In the **Calendar** app, create an event that repeats daily, set its alert type to **Open file**, and pick this HTML file.

Or from a terminal, run `crontab -e` and add a line like this (adjust the path first):

```bash
0 8 * * * open -a "Google Chrome" "/path/to/Cozy_Shelter_Reminder_Studio.html"
```

Remove it later by running `crontab -e` again, deleting that line, and saving.

## Lunar calendar data

Converting a lunar-calendar birthday to its solar-calendar date each year uses a compact conversion table (1900–2050) extracted from [urstory/manseryeok-js](https://github.com/urstory/manseryeok-js) (MIT License), which is itself built on lunar-solar data from KASI (Korea Astronomy and Space Science Institute). The library isn't bundled as-is — only the data this tool needs is embedded directly in the HTML file, with full attribution in the in-app About · Usage dialog.

## Privacy

CSV import, entries, and settings are stored only in this browser's `localStorage` and never sent anywhere — same as the rest of this suite. This tool has no server of its own; it's just a file that runs entirely in your browser. The one exception: if you turn on **AI personalization** in Settings and enter your own API key, your browser calls that provider (Anthropic, OpenAI, Google, or xAI — whichever you pick) directly each time you generate a message. That request goes straight from your browser to the provider you chose, and the key itself is stored only in this browser. Leave it off and the tool never touches the network.

## License

Original code © Hanrim · Cozy Shelter. All rights reserved — free to download and use as-is. No external JavaScript libraries are bundled.

See the in-app **About · Usage** dialog for full attribution details.
