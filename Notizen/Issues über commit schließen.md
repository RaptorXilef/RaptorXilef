# Issues automatisch mit Commits schließen

Du kannst einen **Issue** in GitHub automatisch als gelöst markieren und schließen, indem du spezifische **Schlüsselwörter** in deiner Commit-Nachricht verwendest.

### Wie du einen Issue mit einem Commit automatisch schließt

GitHub erkennt bestimmte Schlüsselwörter in deinen Commit-Nachrichten. Wenn diese Schlüsselwörter zusammen mit der **Nummer des Issues** verwendet werden, wird der Issue nach dem Push des Commits in den **Standard-Branch** (oft `main` oder `master`) geschlossen.

Die gängigsten Schlüsselwörter sind:

* `close`
* `closes`
* `closed`
* `fix`
* `fixes`
* `fixed`
* `resolve`
* `resolves`
* `resolved`

---

### Die gängigsten Schlüsselwörter und ihre Bedeutung
* `close, closes, closed:` Dies sind die generischsten Schlüsselwörter. Sie bedeuten einfach, dass das Issue nun beendet ist. Du verwendest sie, wenn die Arbeit abgeschlossen ist und das Problem nicht mehr existiert.

* `fix, fixes, fixed:` Diese Schlüsselwörter implizieren, dass ein Fehler oder ein Problem behoben wurde. Wenn du also einen Bug-Fix in deinem Commit hast, passen diese Begriffe sehr gut.

* `resolve, resolves, resolved:` Ähnlich wie "fix" deuten diese Schlüsselwörter darauf hin, dass ein Problem oder eine Aufgabe gelöst wurde. Sie können etwas breiter gefasst sein als "fix" und auch für die Erledigung von Feature-Anfragen oder die Klärung von Fragen verwendet werden.

---

### So gehst du vor:

1.  **Erstelle deinen Commit:**
    Arbeite an deinen Änderungen und stage sie dann:

    ```bash
    git add .
    ```

2.  **Verfasse die Commit-Nachricht mit dem Schlüsselwort und der Issue-Nummer:**
    Füge in deiner Commit-Nachricht das Schlüsselwort (z.B. `fixes`) gefolgt von der Raute (`#`) und der Issue-Nummer ein. Die Issue-Nummer ist die Zahl, die du im GitHub-Issue siehst (z.B. `#123`).

    **Beispiel-Commit-Nachricht:**

    ```bash
    git commit -m "feat: Implementierung der Login-Funktion. Fixes #42"
    ```

    Oder:

    ```bash
    git commit -m "refactor: Code-Optimierung für bessere Performance. Closes #15"
    ```

    Du kannst auch **mehrere Issues** in einer Commit-Nachricht schließen:

    ```bash
    git commit -m "fix: Behebung mehrerer kleinerer Fehler. Closes #123, Fixes #124"
    ```

    **Wichtige Punkte zur Platzierung des Schlüsselworts:**
    Das Schlüsselwort muss im Commit-Header (der ersten Zeile der Commit-Nachricht) oder im Commit-Body stehen. Wenn du es im Body verwendest, sollte es auf einer eigenen Zeile stehen, um die Lesbarkeit zu verbessern.

3.  **Pushe deine Änderungen nach GitHub:**
    Sobald du den Commit mit der entsprechenden Nachricht erstellt hast, pushe ihn auf deinen Standard-Branch (z.B. `main`) auf GitHub:

    ```bash
    git push origin main
    ```

---

### Was passiert danach?

Sobald der Commit mit der spezifischen Nachricht in den Standard-Branch gepusht wurde, überprüft GitHub die Commit-Nachricht. Wenn es ein gültiges Schlüsselwort und eine gültige Issue-Nummer findet, wird der verknüpfte Issue automatisch geschlossen. Im Issue wird dann auch vermerkt, welcher Commit ihn geschlossen hat.

**Beispiel für eine gute Commit-Nachricht:**


```bash
feat: Neue Benutzerregistrierung implementiert

Diese Änderung fügt die komplette Logik und das Frontend für die Registrierung neuer Benutzer hinzu.
Es beinhaltet Validierungen für E-Mail und Passwort.

Closes #78
```

Diese Methode ist sehr nützlich, um deinen Workflow zu optimieren und die Issue-Verwaltung direkt in deinen E
