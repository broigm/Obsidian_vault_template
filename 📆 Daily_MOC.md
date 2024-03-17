
Las notas diarias son listados con fecha y hora únicamente para uso personal, la idea es volcar en ellas todo lo que tenga en la cabeza, tanto a nivel profesional como personal para, así, poder centrarme en las tareas que correspondan. Además, me permite ver de un vistazo todas las tareas en función a su fecha. Ya sean atrasadas, para hoy o pendientes.

## Tareas recurrentes

- [ ] Añadir report horas de ayer 🔁 every weekday

## Historico dailys

```dataview
TABLE file.cday as Created
FROM "1.Daily_Notes"
WHERE file.name != this.file.name and file.name != "📝 Notas"
SORT file.cday DESC
```