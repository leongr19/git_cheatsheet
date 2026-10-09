# 🐙 Git Cheatsheet

Eine schnelle Übersicht der wichtigsten Git-Befehle.

## Repository

| Befehl | Beschreibung |
|--------|--------------|
| `git init` | Neues Repository im aktuellen Verzeichnis anlegen |
| `git clone <url>` | Remote-Repository inklusive Historie klonen |
| `git remote -v` | Konfigurierte Remotes anzeigen |
| `git remote add <name> <url>` | Remote unter einem Namen hinzufügen |

## Dateien tracken

| Befehl | Beschreibung |
|--------|--------------|
| `git status` | Änderungen, Staging und ungetrackte Dateien anzeigen |
| `git add <datei>` | Datei in den Staging-Bereich legen |
| `git add .` | Alle Änderungen im Verzeichnis stageen |
| `git commit -m "Nachricht"` | Commit aus gestageten Änderungen erstellen |
| `git commit -am "Nachricht"` | `add` + `commit` in einem Schritt (nur getrackte Dateien) |

## Historie & Änderungen ansehen

| Befehl | Beschreibung |
|--------|--------------|
| `git log` | Commit-Historie anzeigen |
| `git log --oneline --graph --all` | Kompakte graphische Darstellung aller Branches |
| `git diff` | Änderungen zwischen Arbeitsverzeichnis und Staging |
| `git diff --staged` | Änderungen zwischen Staging und letztem Commit |
| `git show <commit>` | Ein einzelnen Commit inkl. Änderungen anzeigen |

## Branches

| Befehl | Beschreibung |
|--------|--------------|
| `git branch` | Alle lokalen Branches auflisten |
| `git branch <name>` | Neuen Branch erstellen |
| `git switch -c <name>` | Neuen Branch erstellen **und** wechseln |
| `git switch <branch>` | Zu bestehendem Branch wechseln |
| `git checkout <branch>` | Branch wechseln (klassische Variante) |
| `git branch -d <name>` | Gemergten Branch löschen |
| `git branch -D <name>` | Branch erzwungenermaßen löschen |

## Remote (GitHub/GitLab)

| Befehl | Beschreibung |
|--------|--------------|
| `git pull` | Neueste Remote-Änderungen holen und mergen |
| `git fetch` | Remote-Änderungen herunterladen, **ohne** zu mergen |
| `git push` | Lokale Commits ins Remote schieben |
| `git push -u origin <name>` | Neuen Branch pushen und mit Remote verknüpfen |
| `git push --force` | Remote-Historie überschreiben (⚠️ gefährlich!) |

## Merge & Rebase

| Befehl | Beschreibung |
|--------|--------------|
| `git merge <branch>` | Branch in aktuellen Branch mergen |
| `git rebase <branch>` | Commits auf Zielbranch versetzen (saubere Historie) |
| `git rebase --continue` | Rebase nach Konfliktlösung fortsetzen |
| `git rebase --abort` | Rebase abbrechen und alten Stand wiederherstellen |

## Rückgängig machen

| Befehl | Beschreibung |
|--------|--------------|
| `git restore <datei>` | Datei auf Staging-Stand zurücksetzen |
| `git restore --staged <datei>` | Datei aus dem Staging entfernen |
| `git checkout -- <datei>` | Alle Änderungen an einer Datei verwerfen |
| `git reset --soft <commit>` | Zurücksetzen, Änderungen bleiben gestaged |
| `git reset --hard <commit>` | Zurücksetzen, **alle Änderungen danach weg** (⚠️) |
| `git revert <commit>` | Commit sicher rückgängig machen (neuer Commit) |

## Sonstiges

| Befehl | Beschreibung |
|--------|--------------|
| `git stash` | Uncommittete Änderungen wegparken |
| `git stash pop` | Geparckte Änderungen wiederherstellen |
| `git tag -a <name> -m "Nachricht"` | Angepinnten Tag erstellen (z. B. `v1.0.0`) |
| `git config --global user.name "Name"` | Git-Namen setzen |
| `git config --global user.email "mail"` | Git-E-Mail setzen |

## ⚡ Typischer Workflow

```bash
git pull                                 # aktuelle Änderungen holen
git switch -c feature/mein-feature       # neuen Branch anlegen
# ... Änderungen in Dateien machen ...
git add .
git commit -m "Feature X hinzugefügt"
git push -u origin feature/mein-feature
# danach Pull Request / Merge Request im Browser erstellen
