---
date: <% tp.file.creation_date() %>
type: meeting
company: 
summary: 
start: <% tp.file.creation_date("HH") %>h<% tp.file.creation_date("mm") %>m
end:
---
tags: [[🗣 Meetings_MOC]], [[👥 Pepople_MOC]]
Daily note: [[<% tp.date.now("YYYY/MM-MMMM/DD-dddd") %>]]
<% await tp.file.move("/2.Notas_Reunión/" + tp.date.now("YYYY-MM-DD") + " " + tp.file.title) %>
# [[<% tp.date.now("YYYY-MM-DD") + " " + tp.file.title %>]]

## 📆  Fecha

<% tp.date.now("DD MMMM YYYY") %>

## 🎫 Request:

## 👥 Asistentes: 

- 
## 🥅 Objetivo

- 

## 🗣 Agenda

- 

## ✍️ Notas

> 

## ✅ Próximos pasos

- 