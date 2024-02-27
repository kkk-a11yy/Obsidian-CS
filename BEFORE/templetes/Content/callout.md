<%*
	const callout_type = await tp.system.suggester(
		["meta","related","link","authors","keywords","hypothesis","methodology","summary","result","context","significance","todoist"],
		["meta","related","link","authors","keywords","hypothesis","methodology","summary","result","context","significance","todoist"]
	)
	const collapsed = await tp.system.suggester(
		["Default (+)","Collapsed View (-)","Open View (+)"],
		["","-","+"]
	)
	const add_custom_title = await tp.system.suggester(
		["Custom Title (N)","Custom Title (Y)"],
		["N","Y"]
	)
	if (add_custom_title === "Y") {
		custom_title = " " + await tp.system.prompt("What is your custom title?")
	} else {
		custom_title = ""
	}
	tR = "> [!" + callout_type + "]" + collapsed + custom_title + "\n> "
_%>