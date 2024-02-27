---
read_book: 
good_reads_review: 
roth_ira: 
youtube_collab: 
ulfar_event: 
social_outing: 
---

# Monthly Review:
%% This template Requires the Templater plugin %%
[[<% tp.date.now("YYYY-[M]MM", "P-1M") %>]] <== <button class="date_button_today">This Month</button> ==> [[<% tp.date.now("YYYY-[M]MM", "P+1M") %>]]

---

```dataview
TABLE aliases
FROM "Journal"
WHERE aliases != null
AND file.day.year = number(substring(this.file.name, 0, 4))
AND dateformat(date(file.name), "yyyy-MM") = replace(this.file.name, "M", "")
SORT file.day
```

---

```dataview
TABLE WITHOUT ID file.day.weekyear AS Week, highlights
FROM "Journal/Daily"
WHERE highlights != null
AND file.day.year = number(substring(this.file.name, 0, 4))
AND dateformat(date(file.name), "yyyy-MM") = replace(this.file.name, "M", "")
SORT file.day
```
