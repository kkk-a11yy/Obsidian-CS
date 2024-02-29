---
videos: <% tp.file.cursor(0) %>
---

# Weekly Review:

%% This template Requires the Templatr plugin and should be run on sundays, if not on sundays, the value offsets should be adjusted %%

[[<% tp.date.now("gggg-[W]ww", -1, tp.file.title, "gggg-[W]ww") %>]] <== <button>This Week</button> ==>  [[<% tp.date.now("gggg-[W]ww", +7, tp.file.title, "gggg-[W]ww") %>]]

## Notes Created This Week

```dataview
TABLE highlights
FROM "BEFORE/Journal/Daily"
WHERE highlights != null
AND file.day.year = number(substring(string(this.file.name), 0, 4))
AND file.day.weekyear = number(substring(string(this.file.name), 6, 8))
SORT file.day
```
