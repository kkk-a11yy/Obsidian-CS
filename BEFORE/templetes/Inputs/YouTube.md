<%"---"%>
tags: 📥️/🎥️/🟥️
publish: true
aliases: 
<%"---"%>
<%*
const url = await tp.system.clipboard()
const response = await fetch(`https://youtube.com/oembed?url=${url}&format=json`)
const data = await response.json()
console.log(data)

const title = data.title.replaceAll("", "").replaceAll('"', '').replaceAll("\\", "").replaceAll("/", "").replaceAll("<", "").replaceAll(">", "").replaceAll(":", "").replaceAll("|", "").replaceAll("?", "")
const author = data.author_name
const author_url = data.author_url
const html = data.html
const thumbnail = data.thumbnail_url

const newPath = "Inbox/" + title
await tp.file.move(newPath)
//const regex = /v=(.*)&/gm
const regex = /(?:https?:\/\/)?(?:www\.)?(?:youtube\.com\/(?:[^\/\n\s]+\/\S+\/|(?:v|e(?:mbed)?)\/|\S*?[?&]v=)|youtu\.be\/)([a-zA-Z0-9_-]{11})/
// R E G E X  D O C U M E N T A T I O N
// - `(?:https?:\/\/)?` matches the optional "http://" or "https://".
// - `(?:www\.)?` matches the optional "[www](http://www/)." part of the URL.
// - `(?:youtube\.com\/(?:[^\/\n\s]+\/\S+\/|(?:v|e(?:mbed)?)\/|\S*?[?&]v=)|youtu\.be\/)` matches different YouTube URL formats.
// - `([a-zA-Z0-9_-]{11})` captures the 11-character video ID.
const m = regex.exec(url)
console.log(m)
-%>

> [!meta]+ Metadata
> source:: [<% title %>](<% url %>)
> channel:: [<% author %>](<% author_url %>)
> released:: 
> watched:: <% tp.date.now() %>
> thumbnail:: ![](<% thumbnail %>)

---

<iframe src="https://www.youtube-nocookie.com/embed/<% m[1] %>?vq=hd1080&modestbranding=1&rel=0&iv_load_policy=3" width="569" height="317" frameborder="0" style="margin: 0 auto; display: block;"></iframe><!-- markdown-link-check-disable-line -->
