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
2. Run `gogcli calendar list --start=today --end=+<days>d`.
3. Display events as: Date/Time, Title, Attendees count, Location (if any).
4. Group events by day.
5. Offer to create a new event or view details of any listed event.
