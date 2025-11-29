# GitHub Repository Setup

## Öffentliches Repository auf GitHub erstellen

1. Gehen Sie zu [GitHub](https://github.com) und melden Sie sich an
2. Klicken Sie auf das "+" Symbol oben rechts und wählen Sie "New repository"
3. Geben Sie den Repository-Namen ein: `civicspaces`
4. Wählen Sie "Public" als Sichtbarkeit
5. **WICHTIG**: Lassen Sie die Optionen "Add a README file", "Add .gitignore" und "Choose a license" **NICHT** aktiviert, da wir bereits lokale Dateien haben
6. Klicken Sie auf "Create repository"

## Lokales Repository mit GitHub verbinden

Nachdem das Repository auf GitHub erstellt wurde, führen Sie folgende Befehle im Terminal aus (im `civicspaces` Verzeichnis):

```bash
git add .
git commit -m "Initial commit: Repository Setup mit README und Struktur"
git branch -M main
git remote add origin https://github.com/IHR-USERNAME/civicspaces.git
git push -u origin main
```

**Hinweis**: Ersetzen Sie `IHR-USERNAME` mit Ihrem GitHub-Benutzernamen.

## Alternative: SSH verwenden

Falls Sie SSH verwenden möchten:

```bash
git remote add origin git@github.com:IHR-USERNAME/civicspaces.git
```


