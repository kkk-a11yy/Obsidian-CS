<%*
	const dvtype = await tp.system.suggester(
		[
			"table",
			"list",
			"task",
			"calendar"
		],[
			"TABLE ",
			"LIST ",
			"TASK ",
			"CALENDAR "
		]
	)
	tR = "```dataview" + "\n" + dvtype
_%>
 <%tp.file.cursor(0)%>
FROM <%tp.file.cursor(1)%>
WHERE <%tp.file.cursor(2)%>
```
<%tp.file.cursor(3)%>