---
tags: ⚙️
aliases: timeline
created: 2022-03-15 2331
updated: 2023-10-29 1845
---

```dataview
LIST rows.file.link
FROM #📥️ AND !"Readwise"
WHERE file.day
SORT file.day
GROUP BY file.day.year
```
