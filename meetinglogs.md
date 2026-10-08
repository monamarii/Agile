## 08-10-2026
Kõne\
Osalejad: Mona, Johanna

### Kokkuvõte
Otsustasime, et liigume edasi **Godot**'i ning **GDScript**'iga\
Godotile sai lisatud [Godot Git plugin](https://github.com/godotengine/godot-git-plugin/wiki/Git-plugin-v3)\
Otsustasime nime osas ära, nimeks jääb nüüdsest: **QuestPets**\
Jira Taskid, Storyd, Spike'id on uuendatud plaani põhjal ümber struktureeritud\
Jätame max. taskide arvuks alustuseks 6 (alati saab hiljem muuta)

### Vaja valik teha
Kas taskid ja loomad on: 

- **ühes fullscreen aknas always-on-top** (peab saama transparent osa alt teistes rakendustes tööd teha, ei tohi segada muid tegevusi)

või 

- **1 aken taskide jaoks ning loomad tulevad subwindow'itena** (ilma taskbarile aknaid juurde tekitamata)


---

## 01-10-2026 
Kohviku sess\
Osalejad: Mona, Johanna

### Tegevusplaan
- Mida päriselt vaja on?
- Paika panna baasfunktsionaalsused (esimene epic)
- Mis tech stack kasutusele tuleb? (Kas Godot või Python/PySide v PyQt)
- Rollid paika panna
- Ennast kurssi viia Jiraga ning korrigeerida backlog

Rakendus peab täitma oma eesmärki, vältima üleliigseid lisasid ning bloati, mille puhul pole täpselt teada, mida see teeb.

---
### Baasfunktionaalsused

(Siia panna nimekeiri baasfunktsionaalsustest)
Järjest tacklime ükshaaval whatever we gotta do ykno
Tutorialid ja Internet on meie sõber

---
### Taskid
- (Scrapped) Taskil on kolm staatust: To Do, In Progress, Completed
- Kui Task on märgitud Completed, siis saab kasutaja +1 coin
- Taskil on: Title, Comment/Description
- Kasutaja sisendil (pealkiri, kommentaar) on nii miinimum kui maksimum tähemärgilimiidid
- Taskid on listina, märkmiku stiilis
- Task, mis on märgitud Completed saab kriipsu peale
strike-through, mingi keybindiga väike popup (taski muutmine, kustutamine?)
- Misiganes keybindide kasuks me otsustame lõpuks


---
### Tehnilised nõuded
- Offline
- Andmed hoiustatud lokaalselt (Local storage)
- Võimalikult vähenõudlik arvuti ressursside osas

---
### Kunsti assetid
- Grid size ja lõppsuurus otsustada
- Värvipaletid
- Animatsioonid loomadel: Idle + Tegutsev
- Max frame arv sprite'idel
- Spritesheet (paneb skriptiga loopima)

