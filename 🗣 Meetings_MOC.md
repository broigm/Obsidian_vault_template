 %% tags: #MOC %% 

# Meetings MOC
Las reuniones son eventos con fecha y hora con otras personas, donde se intercambia y recopila información. Las notas de las reuniones son intrínsecamente efímeras. Se almacenan en un espacio separado del de otras notas (2.Notas_Reunión) y rara vez se revisan. Si hay información en una reunión a la que es necesario acceder más tarde, se debe mover a una nota más permanente.

```meta-bind-button
label: New Meetings
hidden: false
class: ""
tooltip: ""
id: ""
style: primary
actions:
  - type: templaterCreateNote
    templateFile: 6.Templates/Meetings.md
    folderPath: 2.Notas_Reunión
    fileName: TKTK
    openNote: true

```

## Meeting Notes

```dataview
TABLE file.cday as Creado, company as Empresa, (end - start) as Duración, summary as Resumen
FROM "2.Notas_Reunión" and -#MOC
SORT file.cday DESC
```


