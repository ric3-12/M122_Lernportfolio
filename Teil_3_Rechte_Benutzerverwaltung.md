

## 1. Dateirechte – Wer darf was?

Stell dir vor, du hast deine Schulmappe und entscheidest, wer reingucken, was ändern oder sogar damit arbeiten darf. Genauso ist es mit Dateien in Linux!

### 1.1 Wer ist wichtig?
Drei Arten von Leuten sind wichtig:

* **Besitzer**: Das bist du, der die Datei erstellt hat.
* **Gruppe**: Deine Freunde, die auch Zugriff haben sollen.
* **Andere**: Alle anderen auf dem System.

### 1.2 Was bedeuten die Zeichen?
Wenn du `ls -al` eingibst, siehst du so komische Zeichen wie `-rwxr-xr--`. Das bedeutet:

* chmod "Zeichen"
  
    * **`r` (Read)**: Lesen (bei Ordnern: reinschauen).
    * **`w` (Write)**: Schreiben/Ändern (bei Ordnern: was reinlegen/rausnehmen).
    * **`x` (eXecute)**: Ausführen (bei Ordnern: reingehen).
    * Ein `-` heisst, das Recht fehlt.

**Beispiel:** `-rwxr-xr--` heisst:
* Du (Besitzer) darfst alles (lesen, schreiben, ausführen).
* Deine Gruppe darf lesen und ausführen (aber nix ändern).
* Alle anderen dürfen nur lesen.

### 1.3 Wichtige Befehle für Rechte
* **`chown`**: Ändert den **Besitzer** der Datei. (z.B. `chown lina meine_datei`)
* **`chmod`**: Ändert die **Rechte** selbst.
    * Mit Zahlen ist's am einfachsten: `7` für `rwx`, `6` für `rw-`, `5` für `r-x`, `4` für `r--`.
    * `chmod 754 meine_datei` macht die Rechte so: Besitzer 7 (`rwx`), Gruppe 5 (`r-x`), Andere 4 (`r--`).

---

## 2. Benutzer & Gruppen – Wer bin ich und wer gehört dazu?

Es gibt Befehle, um zu checken, wer gerade am Start ist oder um den Benutzer zu wechseln.

### 2.1 Wer bin ich?
* **`whoami`**: Sagt dir, wer du gerade bist.
* **`groups`**: Zeigt, in welchen Gruppen du bist.
* **`id`**: Gibt dir deine ID und deine Gruppen-IDs.

### 2.2 Benutzer wechseln
* **`su - <Benutzername>`**: Damit kannst du dich als ein anderer Benutzer anmelden.

### 2.3 Benutzer-Management (nur für Pros!)
Diese Befehle braucht man nur wenn man Admin:

* **`useradd <Benutzername>`**: Neuen Benutzer erstellen.
* **`userdel <Benutzername>`**: Benutzer löschen.
* **`passwd <Benutzername>`**: Passwort ändern.
* **`logout` / `exit`**: Abmelden.
