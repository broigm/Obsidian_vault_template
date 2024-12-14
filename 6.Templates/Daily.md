---
created: <% tp.file.creation_date() %>
tags:
  - Daily_Notes
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

**Incomming**
```tasks
not done
path includes kanboard
heading includes Incomming
```

### [[kanboard|Añadir tarea]]

## ✅ To Do

- - -

```tasks
not done
no due date
path includes kanboard
heading includes To Do
```


- - - 

### 🏃 Urgente

#### 🔺 Tareas más urgentes

```dataview
TASK FROM "kanboard" WHERE !completed AND contains(text,"🔺")  SORT priority desc GROUP BY section
```
#### ⏫ Tareas de prioridad muy alta

```dataview
TASK FROM "kanboard" WHERE !completed AND contains(text,"⏫")  SORT priority desc GROUP BY section
```

#### 🔼 Tareas de prioridad alta

```dataview
TASK FROM "kanboard" WHERE !completed AND contains(text, "🔼") SORT priority desc GROUP BY section
```

### 🔗 Subtareas por Proyecto

```dataview
TASK FROM "0.Projects" WHERE !completed sort due asc group by project
```


### 🚀 Tareas vencidas de otros días

```dataview
TASK FROM "kanboard" WHERE !completed AND due < this.file.cday & due != null SORT due asc GROUP BY section
```

### ✔ Hoy

```tasks
not done
path includes kanboard
heading includes To Do
due today
```

```dataview
 TASK FROM "kanboard" WHERE !completed AND due = this.file.cday SORT due asc GROUP BY section
```

```dataview
TASK FROM "0.Projects" WHERE !completed AND due = this.file.cday sort due asc group by project
```


#### 🔽 Tareas de prioridad baja

```dataview
TASK FROM "kanboard" WHERE !completed AND contains(text, "🔽") SORT priority desc GROUP BY section
```

#### ⏬ Tareas de prioridad Muy baja

```dataview
TASK FROM "kanboard" WHERE !completed AND contains(text, "⏬") SORT priority desc GROUP BY section
```

- - - 
### ✔ Mañana

```dataview
 TASK FROM "kanboard" WHERE !completed AND due = this.file.cday + dur(1 day) SORT due asc GROUP BY section
```

```dataview
TASK FROM "0.Projects" WHERE !completed AND due = this.file.cday + dur(1 day) sort due asc group by project
```

- - - 
### ✔ Esta semana

```dataview
 TASK FROM "kanboard" WHERE !completed AND due > this.file.cday & due != null AND due != this.file.cday AND due != this.file.cday + dur(1 day) AND due.weekyear = this.file.cday.weekyear AND due.year = this.file.cday.year SORT due asc GROUP BY section
```

```dataview
TASK FROM "0.Projects" WHERE !completed AND due > this.file.cday & due != null AND due != this.file.cday AND due != this.file.cday + dur(1 day) AND due.weekyear = this.file.cday.weekyear AND due.year = this.file.cday.year sort due asc group by project
```

- - - 
### ✔ La próxima semana

```dataview
 TASK FROM "kanboard" WHERE !completed AND due != this.file.cday AND due != this.file.cday + dur(1 day) AND due.weekyear = (this.file.cday.weekyear +1) AND due.year = this.file.cday.year SORT due asc GROUP BY section
```

```dataview
TASK FROM "0.Projects" WHERE !completed AND due != this.file.cday AND due != this.file.cday + dur(1 day) AND due.weekyear = (this.file.cday.weekyear +1) AND due.year = this.file.cday.year sort due asc group by project
```

- - - 
### ✔ Más tarde

```dataview
 TASK FROM "kanboard" WHERE !completed AND due != this.file.cday AND due != this.file.cday + dur(1 day) AND due.weekyear > (this.file.cday.weekyear +1) SORT due asc GROUP BY section
```

```dataview
TASK FROM "0.Projects" WHERE !completed AND due != this.file.cday AND due != this.file.cday + dur(1 day) AND due.weekyear > (this.file.cday.weekyear +1) sort due asc group by project
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
TASK FROM "1.Daily_Notes" WHERE !completed AND !due AND file.cday != this.file.cday and file.name !="Daily MOC" AND !parent GROUP BY section
```


- - -

<% tp.web.daily_quote() %>

---
# ✅ Tareas Completadas hoy

```dataview
 TASK FROM "kanboard" WHERE completed AND checked AND completion = this.file.cday SORT due asc GROUP BY section
```

```dataview
 TASK FROM "0.Projects" WHERE completed AND checked AND completion = this.file.cday SORT due asc GROUP BY project
```

---

<< [[<% fileDate = moment(tp.file.title, 'DD-dddd').subtract(1, 'd').format("[1.Daily_Notes]/YYYY/MM-MMMM/DD-dddd") %>|Yesterday]] | [[<% fileDate = moment(tp.file.title, 'DD-dddd').add(1, 'd').format("[1.Daily_Notes]/YYYY/MM-MMMM/DD-dddd") %>|Tomorrow]] >>
