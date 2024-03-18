---
company: 
location: 
title: 
email: 
website: 
aliases: 
Category:
---
tags:: [[People MOC]]

# <% tp.file.title %>
<% await tp.file.move("/7.Participantes/" + tp.file.title) %>


**Categoría:**

`INPUT[inlineSelect(option(Work), option(Personal), option(Creative), option(Fictional), option(Notable)):Category]`


## Notes
- 

## Meetings
```dataview
TABLE file.cday as Created, summary AS "Summary", category AS "Category"
FROM "2.Notas_Reunión" where contains(file.outlinks, [[<% tp.file.title %>]])
SORT file.cday DESC
```
