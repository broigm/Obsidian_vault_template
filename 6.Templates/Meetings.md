---
date: <% tp.file.creation_date() %>
type: meeting
company: 
summary: 
start: <% tp.file.creation_date("HH") %>h<% tp.file.creation_date("mm") %>m
end: 
tags:
  - Meetings_MOC
---
tags: [[🗣 Meetings_MOC]], [[👥 People_MOC]]
Daily note: [[<% tp.date.now("[1.Daily_Notes]/YYYY/MM-MMMM/DD-dddd", "es") %>|Daily_Note]]

<% await tp.file.move("/2.Notas_Reunión/" + tp.date.now("YYYY-MM-DD") + " " + tp.file.title) %>

**Categoría:**

`INPUT[inlineSelect(option(Work), option(Personal), option(Creative), option(Fictional), option(Notable)):Category]`
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
