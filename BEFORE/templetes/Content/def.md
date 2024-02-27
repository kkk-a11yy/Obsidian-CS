<%*
	const content = await tp.file.selection()
	const choice = await tp.system.suggester(
		["list","term","definition"],
		[
			"<dl>\n" + content + "\n</dl>",
			"\t<dt>" + content + "</dt>\n",
			"\t<dd>" + content + "</dd>\n"
			
		]
	)
	
	tR = choice
_%>