---
tags: ⚙️
publish: false
created: 2022-04-30 0909
updated: 2023-10-16 1256
---

# Table Of Contents

## Todoist

> [!todoist]-
> ```todoist  
> name: My Tasks  
> filter: "today | overdue"  
> sorting:  
> - date  
> - priority  
> group: true
> ```

## Vault Tasks

```dataview
TASK
FROM "" AND !"Z/2023 Goals"
WHERE !completed
GROUP BY file.link
```
