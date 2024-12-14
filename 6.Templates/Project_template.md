---
created: <% tp.file.creation_date() %>
status: 
client: 
published: false
cover: 
technologies: 
done_date: 
finished_at: 
tags: [project]
due_date: ""
company: 
summary: 
daily_note: [[<% tp.date.now("[1.Daily_Notes]/YYYY/MM-MMMM/DD-dddd", "es") %>|Daily_Note]]
request: 
parent: 
type: project
meeting_note:
project: <% tp.file.title %>
---

# Descripción

<% tp.file.cursor() %>

## 📊 Estadísticas del proyecto



```dataviewjs
const projectName = dv.current().file.name;

const tasks = dv.pages().where(page => page.type === "task" && page.project === projectName);
const meetings = dv.pages().where(page => page.type === "meeting" && page.project === projectName);
const analysis = dv.pages().where(page => page.type === "analysis" && page.project === projectName);
const errors = dv.pages().where(page => page.type === "response" && page.project === projectName);
const documentation = dv.pages().where(page => page.type === "documentation" && page.project === projectName);
const scripts = dv.pages().where(page => page.type === "script" && page.project === projectName);

const chartData = {
    type: 'bar',
    data: {
        labels: ['Tareas', 'Reuniones', 'Análisis', 'Errores', 'Documentación', 'Scripts'],
        datasets: [
            {
                label: 'Tareas',
                data: [tasks.length, 0, 0, 0, 0, 0],
                backgroundColor: 'rgba(255, 99, 132, 0.6)',
                borderColor: 'rgba(255, 99, 132, 1)',
                borderWidth: 1
            },
            {
                label: 'Reuniones',
                data: [0, meetings.length, 0, 0, 0, 0],
                backgroundColor: 'rgba(54, 162, 235, 0.6)',
                borderColor: 'rgba(54, 162, 235, 1)',
                borderWidth: 1
            },
            {
                label: 'Análisis',
                data: [0, 0, analysis.length, 0, 0, 0],
                backgroundColor: 'rgba(255, 206, 86, 0.6)',
                borderColor: 'rgba(255, 206, 86, 1)',
                borderWidth: 1
            },
            {
                label: 'Errores',
                data: [0, 0, 0, errors.length, 0, 0],
                backgroundColor: 'rgba(75, 192, 192, 0.6)',
                borderColor: 'rgba(75, 192, 192, 1)',
                borderWidth: 1
            },
            {
                label: 'Documentación',
                data: [0, 0, 0, 0, documentation.length, 0],
                backgroundColor: 'rgba(153, 102, 255, 0.6)',
                borderColor: 'rgba(153, 102, 255, 1)',
                borderWidth: 1
            },
            {
                label: 'Scripts',
                data: [0, 0, 0, 0, 0, scripts.length],
                backgroundColor: 'rgba(255, 159, 64, 0.6)',
                borderColor: 'rgba(255, 159, 64, 1)',
                borderWidth: 1
            }
        ]
    },
    options: {
        responsive: true,
        plugins: {
            legend: {
                display: true,
                labels: {
                    color: 'white' // Cambiar el color del texto si es necesario
                }
            }
        },
        scales: {
            x: {
                stacked: true
            },
            y: {
                beginAtZero: true
            }
        }
    }
};

window.renderChart(chartData, this.container);


```


## 🚀 Productividad del equipo


```dataview
TABLE assigned_to as "Asignado a", length(rows) as "Tareas completadas" WHERE type = "task" AND project = this.file.name AND status = "Done" GROUP BY assigned_to SORT length(rows) DESC
```

## 📑 Documentación 

```dataview
TABLE file.cday as "Creado", summary as "Resumen" 
FROM "0.Projects"
WHERE type = "documentation" AND project = this.file.name 
SORT file.cday ASC
```

## ✅ Tareas asociadas

```dataview
TABLE file.cday as "Creado", status as "Estado", summary as "Resumen"
FROM "0.Projects"
WHERE type = "task" AND project = this.file.name
SORT file.cday ASC
```

## Reuniones
```dataview
TABLE file.cday as "Creado", summary as "Resumen" 
FROM "0.Projects"
WHERE type = "meeting" AND project = this.file.name 
SORT file.cday ASC
```


## Tareas simples

```dataview
TASK WHERE contains(tags, this.file.name)
```

## 🔍 Análisis relacionados
```dataview
TABLE file.cday as "Creado", summary as "Resumen"
FROM "0.Projects"
WHERE type = "analysis" AND project = this.file.name SORT file.cday ASC
```

## ❗ Errores encontrados

```dataview
TABLE file.cday as "Creado", summary as "Resumen"
FROM "0.Projects"
WHERE type = "response" AND project = this.file.name
SORT file.cday ASC
```

## 💻 Scripts relacionados

```dataview
TABLE file.cday as "Creado", summary as "Resumen", technologies as "Tecnologías" WHERE type = "script" AND project = this.file.name SORT file.cday ASC
```
