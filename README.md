# Übung: GitHub ausprobieren

**Ablauf:** Fork → Clone → Datei `erwartungen/<name>.md` anlegen → Commit → Push → Pull Request

> Bearbeite nur deine eigene Datei, dann gibt es keine Konflikte.

## 1. Vorbereitung

Du brauchst einen GitHub Account und ein installiertes Git. Ob Git schon da ist, prüfst du im Terminal mit `git --version`.

<details>
<summary><b>Git auf Windows installieren</b></summary>

1. Lade den Installer von [git-scm.com/download/win](https://git-scm.com/download/win) herunter.
2. Starte ihn und klicke dich mit den Standardeinstellungen durch.
3. Öffne danach ein **neues** Terminal (PowerShell oder Git Bash) und prüfe mit `git --version`.

Alternativ mit winget:
```powershell
winget install --id Git.Git -e --source winget
```
</details>

<details>
<summary><b>Git auf dem Mac installieren</b></summary>

1. Öffne das **Terminal** und gib `git --version` ein.
2. Ist Git noch nicht installiert, fragt macOS automatisch, ob die **Command Line Tools** installiert werden sollen. Klicke auf **Installieren**.
3. Prüfe danach erneut mit `git --version`.

Alternativ mit Homebrew:
```bash
brew install git
```
</details>

Danach einmalig ausführen:
```bash
git config --global user.name "Max Mustermann"
git config --global user.email "max@example.com"
```

## 2. Fork erstellen (Browser)

Oben rechts auf **Fork** → **Create fork**. Dein Fork liegt dann unter `https://github.com/<DEIN_USERNAME>/<REPO_NAME>`.

## 3. Klonen, Datei anlegen, Commit und Push

### Variante A: Terminal

```bash
git clone https://github.com/<DEIN_USERNAME>/<REPO_NAME>.git
cd <REPO_NAME>

# Datei erwartungen/<name>.md anlegen und ausfüllen

git add erwartungen/<name>.md
git commit -m "Erwartungen von <Dein Name>"
git push
```

Fragt GitHub beim Push nach einem Passwort, nutze einen **Personal Access Token** oder `gh auth login`.

### Variante B: VS Code

1. `Strg+Shift+P` (Mac: `Cmd+Shift+P`) → **Git: Clone** → **Clone from GitHub** → deinen Fork wählen → **Open**
2. Im Explorer: Rechtsklick auf `erwartungen` → **New File** → `<name>.md` anlegen, ausfüllen, speichern
3. **Source Control** (`Strg+Shift+G`) → bei der Datei auf **+** klicken (Stage)
4. Commit Nachricht eingeben → **Commit**
5. **Sync Changes** klicken (Push)

## 4. Pull Request erstellen (Browser)

1. Deinen Fork auf GitHub öffnen → **Contribute** → **Open pull request**
2. Richtung prüfen: **base:** Original Repo ← **head:** dein Fork
3. Titel eingeben → **Create pull request**

Fertig! 🎉

## Probleme?

* **`Permission denied` beim Push:** Wahrscheinlich hast du das Original statt deines Forks geklont. Prüfe das mit `git remote -v`.
* **`git` nicht gefunden:** Installiere Git und starte das Terminal neu.
