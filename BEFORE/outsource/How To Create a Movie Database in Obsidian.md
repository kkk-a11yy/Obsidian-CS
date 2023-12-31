---
dg-publish: false
dg-home: false
tags: tech  OMBI  script emoj
authorUrl: "[FromSergio](BEFORE/Person/YouTube/FromSergio.md)"
author: FromSergio
media: youtube
---


#emoj :  windows唤起表情快捷键：win + .

The guide for what we are going over: https://minimal.guide/Guides/Create+a...
Buy Stephan a coffee: https://www.buymeacoffee.com/kepano

Find Stephan at:
Twitter: https://twitter.com/kepano
Github: https://github.com/kepano

OMDb API key : https://www.omdbapi.com/apikey.aspx
Chhoumann's movies.js script - https://github.com/chhoumann/quickadd...

My movie template:
```
poster: {{VALUE:Poster}}
imdbId: {{VALUE:imdbID}}
scoreImdb: {{VALUE:imdbRating}}
length: {{VALUE:Runtime}}
genre: {{VALUE:Genre}}
year: {{VALUE:Year}}
cast: {{VALUE:Actors}}
director: {{VALUE:Director}}
rating:
status:

plot:: {{VALUE:Plot}}

File name format: {{VALUE:fileName}}
```


Stephans Dataview query

```dataview
table without id
 ("![](" + poster + ")") as Poster,
 file.link as Title,
 string(year) as Year,
 "by " + director as Director,
 "⭐ " + scoreImdb as "⭐ IMDB",
 rating
from #movies
where poster != null
```

My dataview query:
``` dataview
table without id
 ("![](" + poster + ")") as Poster,
 file.link as Title,
 year as Year, director as Director,
 "⭐ " + scoreImdb as "⭐ IMDB",
 rating, genre
from "movies"
where contains(status, "complete")

```
