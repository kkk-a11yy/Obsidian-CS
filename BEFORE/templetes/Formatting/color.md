<%*
	const color = await tp.system.suggester(
		["Red","Orange","Yellow","Green","Aqua","Blue","Purple","Light","Grey"],["red","orange","yellow","green","aqua","blue","purple","light","grey"]
	)
	const brightness = await tp.system.suggester(
		["Bright","Neutral","Faded","Light","Grey"],
		["b","n","f","",""]
	)
	tR = "\\color{" + brightness + color + "}"
_%>