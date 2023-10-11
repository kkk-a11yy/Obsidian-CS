
# 找书网站
- [目录搜索](https://kska32.github.io/ebooks/)

# 📜read list

---
```dataview
Table author as Author, ("![|100](" + coverUrl + ")") as Cover, page_length as "Pages", genre, rating, resource
From "书籍/books"
Where contains(status, "to read")
```

---






# 🧐New Author

---

```dataview
TABLE author, date, rating,resource
From "书籍/books"
WHERE contains(author, "")
```
---



