<%*
	// This Template serves to take input from a user and determine
	// if a prefix is to be prepended to the note as well as
	// allowing renaming of the note but defaulting to the files existing name.
	const title_prefix = await tp.system.suggester(
		["🌱 Seedling",
		"🎥 Video",
		"🐦 Tweet",
		"💭 Thought",
		"🎧 Podcast",
		"👤 Person",
		"📜 Paper",
		"📚 Book",
		"📰 Article"], 
		["",
		"+ ",
		"! ",
		"= ",
		"% ",
		"@ ",
		"& ",
		"{ ",
		"( "],
		false,
		"Type of Note"
	)
	let title = await tp.system.prompt("What is the name of your new note?", tp.file.title)
	await tp.file.rename(title_prefix + title)
_%>