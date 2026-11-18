# Übung: GitHub ausprobieren

**Ablauf:** Fork → Clone → Datei `erwartungen/<name>.md` anlegen → Commit → Push → Pull Request

> Bearbeite nur deine eigene Datei, dann gibt es keine Konflikte.

## Vorbereitung

* GitHub Account und installiertes Git (`git --version`)
* Einmalig ausführen:
  ```bash
  git config --global user.name "Max Mustermann"
  git config --global user.email "max@example.com"
  ```

## 1. Fork erstellen (Browser)

Oben rechts auf **Fork** → **Create fork**. Dein Fork liegt dann unter `https://github.com/<DEIN_USERNAME>/<REPO_NAME>`.

## 2. bis 6. Variante A: Terminal

```bash
git clone https://github.com/<DEIN_USERNAME>/<REPO_NAME>.git
cd <REPO_NAME>

# Datei erwartungen/<name>.md anlegen und ausfüllen

git add erwartungen/<name>.md
git commit -m "Erwartungen von <Dein Name>"
git push
```

Fragt GitHub beim Push nach einem Passwort, nutze einen **Personal Access Token** oder `gh auth login`.

## 2. bis 6. Variante B: VS Code

1. `Strg+Shift+P` → **Git: Clone** → **Clone from GitHub** → deinen Fork wählen → **Open**
2. Im Explorer: Rechtsklick auf `erwartungen` → **New File** → `<name>.md` anlegen, ausfüllen, speichern
3. **Source Control** (`Strg+Shift+G`) → bei der Datei auf **+** klicken (Stage)
4. Commit Nachricht eingeben → **Commit**
5. **Sync Changes** klicken (Push)

## 7. Pull Request erstellen (Browser)

1. Deinen Fork auf GitHub öffnen → **Contribute** → **Open pull request**
2. Richtung prüfen: **base:** Original Repo ← **head:** dein Fork
3. Titel eingeben → **Create pull request**

Fertig! 🎉

## Probleme?

* **`Permission denied` beim Push:** Wahrscheinlich hast du das Original statt deines Forks geklont. Prüfe das mit `git remote -v`.
* **`git` nicht gefunden:** Installiere Git und starte das Terminal neu.
