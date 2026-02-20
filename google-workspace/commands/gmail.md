---
description: Search and read Gmail emails
argument-hint: [query]
allowed-tools: [Bash]
---

# Gmail Search

## Arguments
$ARGUMENTS

## Instructions

1. Run `gogcli gmail list --query="$ARGUMENTS" --limit=10` to search emails.
   If no query is given, list the 10 most recent emails.
2. Display results as: From, Subject, Date, Snippet.
3. Ask the user which email to read in full, then run `gogcli gmail read <id>`.
4. Offer to reply, forward, or trash the email.

Always confirm before sending or deleting.
