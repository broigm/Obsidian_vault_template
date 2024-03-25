---
created: <% tp.file.creation_date() %>
tags:
  - Daily
  - Notes
---


<< [[<% fileDate = moment(tp.file.title, 'DD-dddd').subtract(1, 'd').format("[1.Daily_Notes]/YYYY/MM-MMMM/DD-dddd") %>|Yesterday]] | [[<% fileDate = moment(tp.file.title, 'DD-dddd').add(1, 'd').format("[1.Daily_Notes]/YYYY/MM-MMMM/DD-dddd") %>|Tomorrow]] >>

---

## 📅 Preguntas Diarias

### 🌜 Anoche, después del trabajo...

- <% tp.file.cursor() %>

### 🙌 Una cosa que me entusiasma en este momento es...

- 

### 🚀 Planeo lograr hoy...

- 

### 👎 Una cosa con la que estoy luchando hoy es...

- 

---

# 📝 Notas

## <%tp.date.yesterday('dddd DD - MMMM')%>

![[<% fileDate = moment(tp.file.title, 'DD-dddd').subtract(1, 'd').format("[1.Daily_Notes]/YYYY/MM-MMMM/DD-dddd") %>#📝 Notas%>")]]


# ✅ Tareas

```dataview
TASK FROM "1.Daily_Notes" WHERE !completed AND !checked AND !due AND file.cday != this.file.cday and file.name ="Daily MOC" GROUP BY file.link
```

## ✅ To Do

- - -
- [ ] 

- - - 

## 🏃 Urgente

```dataview
TASK FROM "1.Daily_Notes" WHERE !completed AND !checked AND contains(text,"⏫")  SORT priority desc GROUP BY file.link
```
### 🛑 Tareas que deben abordarse de inmediato

```dataview
TASK FROM "1.Daily_Notes" WHERE !completed AND !checked AND contains(text, "🔼") SORT priority desc GROUP BY file.link
```


### 🚀 Tareas vencidas de otros días

```dataview
TASK FROM "1.Daily_Notes" WHERE !completed AND !checked AND due < this.file.cday & due != null SORT due asc GROUP BY file.link
```

### ✔ Hoy

```dataview
 TASK FROM "1.Daily_Notes" WHERE !completed AND !checked AND due = this.file.cday SORT due asc GROUP BY file.link
```

```todoist
name: ✔ Personales por prioridad
filter: today | overdue
sorting: 
- date
- priority
group: true
```


- - - 
### ✔ Mañana

```dataview
 TASK FROM "1.Daily_Notes" WHERE !completed AND !checked AND due = this.file.cday + dur(1 day) SORT due asc GROUP BY file.link
```

```todoist
name: ✔ Personales por prioridad
filter: tomorrow | overdue
sorting: 
- date
- priority
group: true
```

- - - 
### ✔ Esta semana

```dataview
 TASK FROM "1.Daily_Notes" WHERE !completed AND !checked AND due > this.file.cday & due != null AND due != this.file.cday AND due != this.file.cday + dur(1 day) AND due.weekyear = this.file.cday.weekyear AND due.year = this.file.cday.year SORT due asc GROUP BY file.link
```

```todoist
name: ✔ Personales por prioridad
filter: next 5 days | overdue
sorting: 
- date
- priority
group: true
```

- - - 
### ✔ La próxima semana

```dataview
 TASK FROM "1.Daily_Notes" WHERE !completed AND !checked AND due != this.file.cday AND due != this.file.cday + dur(1 day) AND due.weekyear = (this.file.cday.weekyear +1) AND due.year = this.file.cday.year SORT due asc GROUP BY file.link
```

```todoist
name: ✔ Personales por prioridad
filter: next week | overdue
sorting: 
- date
- priority
group: true
```

- - - 
### ✔ Más tarde

```dataview
 TASK FROM "1.Daily_Notes" WHERE !completed AND !checked AND due != this.file.cday AND due != this.file.cday + dur(1 day) AND due.weekyear > (this.file.cday.weekyear +1) SORT due asc GROUP BY file.link
```


---

## 📝 Notas creadas hoy

```dataview
List FROM "" WHERE file.cday = date("<%tp.date.now('YYYY-MM-DD')%>") SORT file.ctime asc
```


## 📝 Notas modificadas hoy

```dataview
List FROM "" WHERE file.mday = date("<%tp.date.now('YYYY-MM-DD')%>") SORT file.mtime asc
```


- - - 

# 🫂 Estar en contacto con

```dataview
TASK FROM "1.Daily_Notes" WHERE !completed AND !checked AND !due AND file.cday != this.file.cday and file.name !="Daily MOC" AND !parent GROUP BY file.link
```

# ✅ Tareas Completadas hoy

```dataview
 TASK FROM "1.Daily_Notes" WHERE completed AND checked AND completion = this.file.cday SORT due asc GROUP BY file.link
```
---

- - -

<% tp.web.daily_quote() %>

---


<< [[<% fileDate = moment(tp.file.title, 'DD-dddd').subtract(1, 'd').format("[1.Daily_Notes]/YYYY/MM-MMMM/DD-dddd") %>|Yesterday]] | [[<% fileDate = moment(tp.file.title, 'DD-dddd').add(1, 'd').format("[1.Daily_Notes]/YYYY/MM-MMMM/DD-dddd") %>|Tomorrow]] >>
