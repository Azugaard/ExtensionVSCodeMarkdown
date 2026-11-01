# Markdown Visualizer

Une extension VS Code qui affiche un aperçu de tes documents Markdown avec diagrammes **Mermaid**, formules **KaTeX** et diaporamas **Marp**, et qui gère une bibliothèque de modèles réutilisables.

> Projet personnel en cours de développement (version 0.0.1).

## Fonctionnalités

- **Aperçu Markdown** ouvert depuis le bouton de la barre de titre de l'éditeur (visible sur les fichiers Markdown) ou via la commande `markdown Preview`.
- **Rendu** : Markdown, diagrammes Mermaid, formules KaTeX et présentations Marp.
- **Export PDF** du document ouvert (commande `Export Markdown to PDF`).
- **Modèles** : une vue dédiée dans la barre latérale pour créer, copier, modifier et supprimer des modèles, rangés par catégories (stockés dans `templates.json`).

## Réglages

Dans les paramètres VS Code, section *Markdown Visualizer* :

| Réglage | Valeurs | Défaut |
|---|---|---|
| `visualizer.preview.mermaidTheme` | `default`, `dark`, `forest`, `neutral`, `base` | `default` |
| `visualizer.preview.updateMode` | `onType` (à la frappe), `onSave` (à l'enregistrement) | `onType` |
| `visualizer.preview.fontSize` | de 10 à 40 | 16 |

## Installation depuis les sources

Prérequis : VS Code 1.97 ou plus, Node.js.

```bash
git clone https://github.com/Azugaard/ExtensionVSCodeMarkdown.git
cd ExtensionVSCodeMarkdown
npm install
```

Ouvre le dossier dans VS Code et appuie sur **F5** : une fenêtre « Extension Development Host » s'ouvre avec l'extension chargée.

L'export PDF utilise un navigateur téléchargé séparément, que prépare le script `npm run preparer-navigateurs`.

## Développement

```bash
npm run lint   # analyse du code avec ESLint
npm test       # tests via vscode-test (lance le lint avant)
```

## Structure

- `extension.js` : point d'entrée (commandes, vue des modèles, surveillance de `templates.json`)
- `renderer.mjs`, `scroll.js`, `templates.json` : rendu, synchronisation du défilement, modèles par défaut
- `scripts/` : préparation des navigateurs pour l'export PDF
- `test/` : tests de l'extension

## Technologies

JavaScript, API VS Code (WebView, vue en arbre), markdown-it, KaTeX, Mermaid, Marp, Puppeteer, ESLint.
