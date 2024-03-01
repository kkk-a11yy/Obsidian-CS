---
tags:
  - ⚙️
aliases:
  - timeline
created: 2024-3-1 1337
updated: 2024-3-1 1337
---

```dataview
LIST rows.file.link
FROM #📥️ AND !"Readwise"
WHERE file.day
SORT file.day
GROUP BY file.day.year
```
