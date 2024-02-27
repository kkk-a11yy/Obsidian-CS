<%*
	const lang = await tp.system.suggester(
		[
			"none",
			"bash",
			"css",
			"git",
			"html",
			"javascript",
			"lisp",
			"python",
			"r"
		],[
			"",
			"bash",
			"css",
			"git",
			"html",
			"js",
			"lisp",
			"python",
			"r"
		]
	)
	tR = "```" + lang + "\n"
_%>
<%tp.file.cursor(0)%>
```