
# Lernportfolio M122 – Teil 2: Bash-Skripting & Programmierlogik

## Beispiel-Skript

Ein typisches Bash-Skript (z. B. `install_bsp.sh`) kann:
- Treiber/Software automatisch installieren
- Hardware erkennen
- Rechte setzen und Backups machen

**Bestandteile erkennen:** Variablen, Kontrollstrukturen, Kommentare, Funktionen

---

## Mein erstes Skript

```bash
touch meinscript.sh        # Datei anlegen
nano meinscript.sh         # Datei mit Editor öffnen
```

Inhalt:
```bash
#!/bin/bash
echo "Das ist mein erstes Script"
```

Datei ausführbar machen:
```bash
chmod +x meinscript.sh
./meinscript.sh
```

**Tipp:** `#!/bin/bash` = Shebang (ausführender Interpreter)  
`which bash`, `$SHELL`, `bash --version` → Pfad zur Shell anzeigen

---

## Editoren

-  `nano`, `vi`

---

## Variablen

- Zuweisung: `varname=Wert`
- Zugriff: `$varname`
- Änderung möglich, auch Zuweisung von Befehlsausgabe: `datum=$(date +%Y_%m_%d)`
- Konstanten: `readonly varname=Wert`
- Case-Sensitive: `$VAR` ≠ `$var`

**Beispiel:**
```bash
name="Hans"
echo $name
readonly var="fix"
```

### Wichtige automatische Variablen

| Variable     | Bedeutung                                 |
|--------------|--------------------------------------------|
| `$0`         | Skriptname                                 |
| `$1`–`$9`, `$*` | Übergabeparameter                      |
| `$#`         | Anzahl Parameter                           |
| `$$`         | Prozess-ID                                 |
| `$?`         | Rückgabewert des letzten Befehls           |
| `$PWD`, `$OLDPWD` | Aktuelles / Vorheriges Verzeichnis  |
| `$HOME`      | Home-Verzeichnis                           |
| `$PATH`      | Suchpfad                                   |
| `$RANDOM`    | Zufallszahl (0–32767)                      |
| `$SECONDS`   | Sekunden seit Start der Shell              |

---

## Zeichenketten & Textverarbeitung

- Tools: `expr`, `cut`, `tr`, `paste`, `sed`, `awk`
- Universell einsetzbar für Textmanipulation

---

### 🔁 Schleifen

#### `for` über Parameter

```bash
for file in "$@"; do
  echo $file
done
```

#### `for` über Dateien

```bash
for file in *.txt; do
  echo $file
done
```

#### `for` über Dateiinhalt

```bash
for user in $(cat .userlist); do
  who | grep ^$user > /dev/null && echo "User $user online"
done
```

---

## Ein-/Ausgabe & Umleitungen

| Kanal   | Beschreibung            |
|---------|-------------------------|
| `0`     | stdin (Eingabe)         |
| `1`     | stdout (Ausgabe)        |
| `2`     | stderr (Fehlerausgabe)  |

### Ausgabe umleiten

```bash
ls -la > out.txt           # Überschreibt
cat a.txt >> out.txt       # Hängt an
./script.sh 2> fehler.txt  # Fehler in Datei
./script.sh > out.txt 2>&1 # Fehler + Ausgabe in eine Datei
./script.sh > /dev/null    # Alles unterdrücken
```

### Eingabe umleiten

```bash
cat < input.txt
cat < input.txt > kopie.txt
sort << EOF
Z
A
B
EOF
```

---

## Pipeline (|)

- Übergibt stdout → stdin des nächsten Befehls
- Textbasiert, nicht objektorientiert (wie PowerShell)

```bash
cat file.txt | grep hallo | uniq | sort
cat /etc/passwd | grep -v irc | cut -d ':' -f 1
```

---

## Skripte debuggen

- Mit `bash -x script.sh` debuggen
- Fehlerquellen: Syntax, Rechte, Umleitungen, Pfade, …
