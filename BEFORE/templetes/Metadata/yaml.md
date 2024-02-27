<%*
	const yaml = await tp.system.suggester(
		[
			"0 Standard Block",
		    "full",
			"tags",
			"publish",
			"aliases",
			"cssclass",
			"created",
			"updated",
			"type",
			"status",
			"authors",
			"general_subject",
			"specific_subject",
			"isbn",
			"doi",
			"publish_date",
			"url",
			"citekey",
			"keywords"
		],[
			"tags: \npublish: true\naliases: ",
			"---\ntags: \npublish: true\naliases: \n---\n",
			"tags: ",
			"publish: ",
			"aliases: ",
			"cssclass: ",
			"created: ",
			"updated: ",
			"type: ",
			"status: ",
			"authors: ",
			"general_subject: ",
			"specific_subject: ",
			"isbn: ",
			"doi: ",
			"publish_date: ",
			"url: ",
			"citekey: ",
			"keywords: "
		]
	)
	tR = yaml
_%>
<%tp.file.cursor(0)%>