<%* if (tp.file.title.charAt(0) == "{") { %>
<%-tp.file.include("[[Book]]")%>
<%* } else if (tp.file.title.charAt(0) == "@") { %>
<%-tp.file.include("[[Templates/Inputs/Person]]")%>
<%* } else if (tp.file.title.charAt(0) == "!") { %>
<%-tp.file.include("[[Tweet]]")%>
<%* } else if (tp.file.title.charAt(0) == "%") { %>
<%-tp.file.include("[[Podcast]]")%>
<%* } else if (tp.file.title.charAt(0) == "+") { %>
<%-tp.file.include(await tp.system.suggester(["YouTube","Other"],["[[YouTube]]","[[Video]]"], false, "Video Template")) %>
<%* } else if (tp.file.title.charAt(0) == "(") { %>
<%-tp.file.include("[[Templates/Inputs/Article]]")%>
<%* } else if (tp.file.title.charAt(0) == "&") { %>
<%-tp.file.include("[[Paper]]")%>
<%* } else if (tp.file.title.charAt(0) == "=") { %>
<%-tp.file.include("[[Thought]]")%>
<%* } else { %>
<%-tp.file.include("[[New]]")%>
<%* } _%>