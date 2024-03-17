[[Home]] #MOC

```meta-bind-button
label: Participantes
hidden: false
class: ""
tooltip: ""
id: ""
style: primary
actions:
  - type: templaterCreateNote
    templateFile: 6.Templates/Participants.md
    folderPath: 7.Participantes
    fileName: TKTK
    openNote: true

```


# People MOC
A personal CRM. People Notes are about jotting down notable information about people and linking people back to [[🗣 Meetings_MOC]].

These are the different categories of People Notes:
- Work
- Personal
- Creative
- Fictional
- Notable

---
### Templates
- [[Template, People]]

# People
```dataview
table title
from "7.Participantes"
sort file.name asc
```