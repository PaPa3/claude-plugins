---
description: Search and read Gmail emails
argument-hint: [query]
allowed-tools: [Bash]
---

# Gmail Search

## Arguments
$ARGUMENTS

## Instructions

1. Run `gog gmail search "$ARGUMENTS"` to search emails.
   If no query is given, run `gog gmail search "in:inbox"` to list recent inbox emails.
2. Display results as: From, Subject, Date, Snippet.
3. Ask the user which email to read in full, then run `gog gmail get <id>`.
4. Offer to reply or trash the email.

Always confirm before sending or deleting.
