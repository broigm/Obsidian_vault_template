---
company: 
location: 
title: 
email: 
website: 
aliases: 
---
tags:: [[People MOC]]

# <% tp.file.title %>
<% await tp.file.move("/7.Participantes/" + tp.file.title) %>

## Notes
- 

## Meetings
```dataview
TABLE file.cday as Created, summary AS "Summary"
FROM "2.Notas_Reunión" where contains(file.outlinks, [[<% tp.file.title %>]])
SORT file.cday DESC
```