---
created: 2023-03-10 2016
updated: 2023-11-09 1342
---

## Unprocessed Items

```dataview
LIST rows.file.link
FROM "Readwise"
WHERE file.name != "Readwise Syncs"
WHERE file.day > date("2023-01-01")
AND file.day != null
AND file.day != date("2023-08-07")
AND file.day != date("2023-11-07")
GROUP BY file.day
SORT file.day
```

%%
2023-08-07 | What i mean when i say im autistic
2023-11-07 | Mental Health Toolkit — Tools to Bolster Your Mood and Mental Health
%%
