---
description: List upcoming Google Calendar events
argument-hint: [days=7]
allowed-tools: [Bash]
---

# Google Calendar

## Arguments
$ARGUMENTS

## Instructions

1. Parse the argument as the number of days to look ahead (default: 7).
2. Run `gog calendar events --days=<days>` to list events from the primary calendar.
   - To include all calendars, add `--all`.
   - To filter by text, add `--query=<text>`.
3. Display events as: Date/Time, Title, Attendees count, Location (if any).
4. Group events by day.
5. Offer to view details of any listed event with `gog calendar event <calendarId> <eventId>`.
