# Uebung: GitHub ausprobieren

In dieser Uebung lernst du den typischen Ablauf, wie man auf GitHub zu einem fremden Projekt beitraegt:

**Fork → Clone → Datei anlegen → Commit → Push → Pull Request**

Nebenbei erfahre ich, was du dir von der Vorlesungsreihe erwartest und welche Themen dich interessieren. 🙂


## Deine Aufgabe

1. Erstelle einen **Fork** dieses Repositories.
2. **Clone** deinen Fork auf deinen Rechner.
3. Lege im Ordner `erwartungen/` eine neue Datei `<name>.md` an, z.B. `erwartungen/max_mustermann.md`.
4. Schreibe dort deine **Erwartungen an die Vorlesung** und deine **Themenwuensche** hinein (Vorlage siehe unten).
5. **Committe** die Datei.
6. **Pushe** sie in deinen Fork.
7. Erstelle einen **Pull Request** an dieses Repository.

> **Wichtig:** Bearbeite nur deine eigene Datei. So gibt es keine Konflikte mit den Dateien deiner Kommilitonen.


## Vorlage fuer deine Datei

Kopiere das hier in deine `<name>.md` und fuelle es aus:

```markdown
# Max Mustermann

## Meine Erwartungen an die Vorlesung
* ...
* ...

## Themenwuensche
* ...
* ...

## Meine Vorerfahrung mit Git/GitHub
* keine / ein bisschen / regelmaessig
```


## Voraussetzungen

* Ein **GitHub Account** (kostenlos auf [github.com](https://github.com))
* **Git** ist installiert. Pruefen kannst du das im Terminal mit:
  ```bash
  git --version
  ```
  Falls nicht installiert: [git-scm.com/downloads](https://git-scm.com/downloads)
* Fuer Variante B: **Visual Studio Code** ([code.visualstudio.com](https://code.visualstudio.com))

Einmalig solltest du Git sagen, wer du bist (diese Angaben stehen spaeter in deinen Commits):

```bash
git config --global user.name "Max Mustermann"
git config --global user.email "max@example.com"
```


## Schritt 1: Fork erstellen (im Browser, fuer beide Varianten gleich)

Ein Fork ist deine **eigene Kopie** dieses Repositories in deinem GitHub Account. Dort darfst du alles aendern, ohne das Original zu beruehren.

1. Oeffne dieses Repository auf GitHub.
2. Klicke oben rechts auf **Fork**.
3. Bestaetige mit **Create fork**.

Du landest jetzt auf `https://github.com/<DEIN_USERNAME>/<REPO_NAME>`. Das ist dein Fork.


## Variante A: Mit Git im Terminal

### 2. Fork clonen

Auf der Seite deines Forks: Klick auf den gruenen Button **Code** und kopiere die HTTPS URL.

```bash
git clone https://github.com/<DEIN_USERNAME>/<REPO_NAME>.git
cd <REPO_NAME>
```

### 3. Datei anlegen

Lege die Datei `erwartungen/<name>.md` mit einem Editor deiner Wahl an und fuelle die Vorlage aus.

Danach kannst du nachsehen, was Git bemerkt hat:

```bash
git status
```

Deine neue Datei sollte rot als *untracked* angezeigt werden.

### 4. Datei zum Commit vormerken (Staging)

```bash
git add erwartungen/<name>.md
git status
```

Jetzt ist die Datei gruen, also bereit fuer den Commit.

### 5. Commit erstellen

```bash
git commit -m "Erwartungen von <Dein Name> hinzugefuegt"
```

Ein Commit ist ein **Schnappschuss** deiner Aenderungen mit einer Beschreibung. Bisher existiert er nur lokal auf deinem Rechner.

### 6. Push zu GitHub

```bash
git push
```

Damit landet dein Commit in deinem Fork auf GitHub.

> **Login beim Push:** GitHub akzeptiert beim Push kein normales Passwort mehr. Meist oeffnet sich automatisch ein Browserfenster zum Anmelden. Falls nicht, nutze einen **Personal Access Token** (GitHub → Settings → Developer settings → Personal access tokens) statt des Passworts, oder melde dich mit der GitHub CLI an: `gh auth login`.

### 7. Pull Request erstellen

Weiter geht es unten bei **Schritt 7: Pull Request erstellen**.


## Variante B: Mit Visual Studio Code

### 2. Fork clonen

1. Oeffne VS Code.
2. Oeffne die Befehlspalette mit `Strg+Shift+P` (Mac: `Cmd+Shift+P`) und waehle **Git: Clone**.
3. Waehle **Clone from GitHub** und melde dich bei GitHub an, wenn VS Code danach fragt.
   Alternativ kannst du die URL deines Forks direkt einfuegen: `https://github.com/<DEIN_USERNAME>/<REPO_NAME>.git`
4. Waehle einen Speicherort auf deinem Rechner.
5. Klicke auf **Open**, um den geclonten Ordner zu oeffnen.

### 3. Datei anlegen

1. Im **Explorer** (links, Dateisymbol) Rechtsklick auf den Ordner `erwartungen` → **New File**.
2. Nenne die Datei `<name>.md`, fuelle die Vorlage aus und speichere mit `Strg+S`.

### 4. Datei zum Commit vormerken (Staging)

1. Wechsle links zur **Source Control** Ansicht (Symbol mit den Verzweigungen, oder `Strg+Shift+G`).
2. Unter **Changes** siehst du deine neue Datei mit einem **U** (untracked).
3. Fahre mit der Maus ueber die Datei und klicke auf das **+** (Stage Changes).
   Die Datei wandert nach **Staged Changes**.

### 5. Commit erstellen

1. Schreibe oben in das Textfeld eine Commit Nachricht, z.B. `Erwartungen von <Dein Name> hinzugefuegt`.
2. Klicke auf **Commit** (oder `Strg+Enter`).

### 6. Push zu GitHub

1. Klicke auf **Sync Changes** (erscheint nach dem Commit an der Stelle des Commit Buttons).
   Alternativ: Klick auf die drei Punkte **…** → **Push**.
2. Falls VS Code nach einer Anmeldung bei GitHub fragt: Erlauben und im Browser bestaetigen.

### 7. Pull Request erstellen

Weiter geht es direkt hier drunter.

> **Tipp:** Mit der Erweiterung **GitHub Pull Requests** kannst du den Pull Request auch direkt in VS Code erstellen. Der Weg ueber den Browser ist aber fuer den Anfang am uebersichtlichsten.


## Schritt 7: Pull Request erstellen (im Browser, fuer beide Varianten gleich)

Mit einem Pull Request bittest du die Besitzer des Original Repositories, deine Aenderungen zu uebernehmen.

1. Oeffne deinen Fork auf GitHub: `https://github.com/<DEIN_USERNAME>/<REPO_NAME>`
2. Dort erscheint meist ein Hinweis *"This branch is 1 commit ahead"* mit dem Button **Contribute** → **Open pull request**.
   Alternativ: Reiter **Pull requests** → **New pull request**.
3. Pruefe die Richtung:
   **base repository:** das Original Repository ← **head repository:** dein Fork
4. Gib einen Titel ein, z.B. `Erwartungen von <Dein Name>`, und optional eine kurze Beschreibung.
5. Klicke auf **Create pull request**.

**Fertig!** 🎉 Ich schaue mir die Pull Requests an und merge sie.


## Kleines Glossar

* **Repository (Repo):** Ein Projektordner mit der kompletten Versionsgeschichte
* **Fork:** Deine eigene Kopie eines fremden Repos auf GitHub
* **Clone:** Ein Repo von GitHub auf deinen Rechner herunterladen
* **Staging** (`git add`): Aenderungen fuer den naechsten Commit vormerken
* **Commit:** Ein gespeicherter Schnappschuss deiner Aenderungen, lokal
* **Push:** Lokale Commits zu GitHub hochladen
* **Pull Request (PR):** Anfrage, deine Aenderungen ins Original Repo zu uebernehmen
* **Merge:** Aenderungen aus einem PR werden uebernommen


## Probleme?

* **`git` wird nicht gefunden:** Git ist nicht installiert oder das Terminal muss nach der Installation neu gestartet werden.
* **`Permission denied` beim Push:** Du hast vermutlich das Original Repo statt deines Forks geclont. Pruefe mit `git remote -v`, ob dort dein Username steht.
* **Pull Request zeigt fremde Dateien:** Pruefe, ob du wirklich nur deine eigene Datei angelegt hast.

Bei allen anderen Fragen: einfach melden!
