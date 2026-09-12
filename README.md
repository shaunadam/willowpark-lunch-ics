# Willow Park Lunch — ICS feed

`willowpark_menu.ics` is a generated calendar feed of the Willow Park School (CBE)
cafeteria menu, scraped from https://willowpark.cbe.ab.ca/cafeteria-menu.

It's kept up to date by a scheduled Claude Code cloud routine (not a GitHub Action) that
re-fetches the page, re-reads the menu tables, and overwrites this file — regenerated from
scratch each run, not incrementally patched. The source page has no year in its date labels
and is maintained by hand by school staff, so formatting/structure can vary week to week.

Consumed by Home Assistant's `remote_calendar` integration as a plain ICS subscription, the
same way every other calendar in that config is set up — pointed at this file's raw URL:

```
https://raw.githubusercontent.com/shaunadam/willowpark-lunch-ics/main/willowpark_menu.ics
```

This repo is public only because the ICS content (a public school's public lunch menu) is
not sensitive — it exists purely to give Home Assistant a stable HTTP URL to poll.
