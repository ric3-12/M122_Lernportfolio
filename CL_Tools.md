

### **REGEX (Reguläre Ausdrücke)**
Zum **spezifischen Suchen** und Mustererkennen in Texten. Es ist eine **Sprache für Suchmuster**, die von Tools wie `grep`, `sed` oder `awk` verwendet wird.

---

### **GREP**
 **Findet** **Zeilen**, die einem bestimmten Muster (REGEX) entsprechen.
**Wichtigste Commands:**
* `grep "Muster" datei.txt`: Sucht nach "Muster" in `datei.txt`.
* `grep -r "Muster" verzeichnis/`: Sucht rekursiv in einem Verzeichnis.
* `grep -i "Muster" datei.txt`: Ignoriert Groß-/Kleinschreibung.
* `grep -v "Muster" datei.txt`: Zeigt Zeilen an, die **nicht** dem Muster entsprechen.

---

### **CUT**
**Schneidet Text** (Zeichen, Felder, Spalten) aus Zeilen aus.
**Wichtigste Commands:**
* `cut -c 1-5 datei.txt`: Schneidet die Zeichen 1 bis 5 aus.
* `cut -d ':' -f 1 datei.txt`: Schneidet das erste Feld (Spalte) basierend auf dem Trennzeichen `:` aus.
**Gegenstück:** `paste` (fügt Spalten zusammen).

---

### **SED**
**Bearbeitet Textströme** (löschen, ersetzen, einfügen von Zeichen/Zeilen). Ideal für automatisierte Textmanipulationen.
**Wichtige Commands:**
* `sed 's/alt/neu/' datei.txt`: Ersetzt das erste Vorkommen von "alt" durch "neu" pro Zeile.
* `sed 's/alt/neu/g' datei.txt`: Ersetzt **alle** Vorkommen von "alt" durch "neu" pro Zeile.
* `sed '/Muster/d' datei.txt`: Löscht Zeilen, die "Muster" enthalten.
**Alternative zum Ersetzen von Zeichen:** `tr` (ersetzt einzelne Zeichen).

---

### **AWK**
**Leistungsstarke** **Programmiersprache** zur Textverarbeitung, ideal für die Analyse und Manipulation von strukturierten Daten (z.B. Log-Dateien, Tabellen).
**Wichtige Konzepte:** Arbeitet mit Feldern ($1, $2 etc.), kann Bedingungen prüfen und Aktionen ausführen.
**Wichtiger Command:**
* `awk '{print $1, $3}' datei.txt`: Gibt das erste und dritte Feld jeder Zeile aus.
* `awk '/Muster/ {print $0}' datei.txt`: Gibt Zeilen aus, die dem Muster entsprechen.

---

### **CURL**
**Überträgt Daten** von oder zu Servern. Oft genutzt, um Webseiten herunterzuladen oder mit APIs zu interagieren.
**Wichtige Commands:**
* `curl https://beispiel.com`: Lädt den Inhalt von `beispiel.com` herunter.
* `curl -O https://beispiel.com/datei.zip`: Lädt eine Datei unter ihrem Originalnamen herunter.
* `curl -X POST -d "daten" https://api.beispiel.com`: Sendet Daten per POST-Anfrage.

---

### **XARGS**
**Wofür?** **Konvertiert Standardeingabe in Argumente** für andere Befehle. Nützlich, um die Ausgabe eines Befehls als Eingabe für einen anderen zu verwenden.
**Wichtige Commands:**
* `find . -name "*.txt" | xargs rm`: Findet alle `.txt`-Dateien und löscht sie.
* `ls | xargs -I {} mv {} {}.bak`: Benennt jede Datei im aktuellen Verzeichnis um, indem `.bak` angehängt wird.

---
