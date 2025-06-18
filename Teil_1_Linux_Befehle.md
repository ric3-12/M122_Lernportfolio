
#  Lernportfolio M122 – Teil 1: Linuxbefehle

---

## Der Linux Prompt & Terminal-Bedienung

- Prompt-Format:  
  `janis@root:home$`  
  z. B. `user@host:~$`
- `~` steht für das Home-Verzeichnis, meist unter `/home/<benutzer>` – Ausnahme: `root` → `/root/`
- Wichtige Sonderzeichen:
  - `;` – mehrere Befehle in einer Zeile
  - `|` – Piping (Befehle verketten)
  - `#` – Kommentar
  - `\` – Zeilenumbruch oder Escape-Zeichen
  - `&` – führt Befehle im Hintergrund aus

---

## Hilfe zu Befehlen

| Befehl              | Beschreibung                                   |
|---------------------|------------------------------------------------|
| `man <cmd>`         | Manual-Page eines Befehls                      |
| `info <cmd>`        | Ausführlichere Hilfe bei GNU-Tools             |
| `whatis <cmd>`      | Kurze Beschreibung eines Befehls              |
| `apropos <Stichwort>` | Durchsucht Hilfeseiten                      |
| `which <cmd>`       | Zeigt Pfad zum installierten Programm         |
| `--help` oder `-h`  | Hilfe direkt vom Befehl selbst                |
| `history`           | Liste aller bisher verwendeten Befehle       |

---

## Verzeichnisnavigation

| Befehl        | Zweck                                           |
|---------------|------------------------------------------------|
| `pwd`         | Aktuelles Verzeichnis anzeigen                 |
| `cd`          | Verzeichnis wechseln                           |
| `mkdir`       | Neues Verzeichnis erstellen                    |
| `rmdir`       | Leeres Verzeichnis löschen                     |
| `ls`          | Inhalt eines Verzeichnisses anzeigen           |
| `find`        | Dateien suchen und optional verarbeiten        |

### Pfadangaben

- **Absolut:** beginnt mit `/` → z. B. `/home/user/data`
- **Relativ:** ab aktuellem Pfad → z. B. `../data`

---

## Dateimanipulation

| Befehl               | Beschreibung                                |
|----------------------|---------------------------------------------|
| `cp`                 | Kopieren von Dateien/Verzeichnissen         |
| `rm`, `rm -r`        | Löschen von Dateien/Verzeichnissen (Vorsicht!) |
| `mv`                 | Verschieben/Umbenennen                      |
| `touch`              | Neue, leere Datei erstellen                 |
| `cat`                | Inhalt anzeigen                             |
| `wc -l`, `wc -w`     | Zeilen bzw. Wörter zählen                   |
| `echo`               | Zeichenkette ausgeben                       |

---

## Aliase (Kurzbefehle)

- Syntax: `alias kurzname="befehl"`
- Beispiel:
  ```bash
  alias gohome="cd ~"
  alias ll="ls -alFG"
  ```

---

## Wildcards & Brace Expansion

| Syntax            | Bedeutung                                      |
|-------------------|-----------------------------------------------|
| `*`               | Beliebig viele Zeichen                        |
| `?`               | Genau ein Zeichen                             |
| `{a,b}`           | Erstellt Kombinationen: `Filea`, `Fileb`      |
| `{1..3}`          | Zahlenbereich: `File1`, `File2`, `File3`      |
| Verschachtelt     | `file{a{1,2},b{3,4}}` → `filea1`, `filea2`, `fileb3`, `fileb4` |

---

## Tilde Expansion

| Ausdruck     | Bedeutung                                 |
|--------------|--------------------------------------------|
| `~`          | Aktuelles Homeverzeichnis (`$HOME`)        |
| `~benutzer`  | Homeverzeichnis eines anderen Benutzers    |
| `~+`         | Aktuelles Verzeichnis (`$PWD`)             |
| `~-` oder `-`| Vorheriges Verzeichnis (`$OLDPWD`)         |
