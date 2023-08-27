---
dg-publish: true
dg-home: true
tags: library 
authorUrl: "[FromSergio](BEFORE/Person/YouTube/FromSergio.md)"
author: FromSergio
file-time: 2023-06-26
---

My book search plugin config:

title: {{title}}
author: {{author}}
category: {{category}}
publisher: {{publisher}}
publishdate: {{publishDate}}
pages: {{totalPage}}
cover: {{coverUrl}}
rating:
date read:
status:

My book database dataview query: 

```dataview
Table author as Author, ("![|100](" + cover + ")") as Cover, pages, category as genre, rating
From "books"
Where contains(status, "complete")
```

 read list :

```dataview
Table author as Author, ("![|100](" + cover_url + ")") as Cover, page_length as "Pages", genre, rating
From "books"
Where contains(status, "to read")
```

New Author Themplate 

```dataview
TABLE author, date, rating
From "books"
WHERE contains(author, "")
```