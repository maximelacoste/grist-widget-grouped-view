# grist-widget-grouped-view

> Grist custom widget — collapsible grouped view. Groups records by any column with fold/unfold, sort by name or count, stable color per group, and persisted options via `grist.setOption()`.

---

## 🇫🇷 Français

### Présentation

Widget personnalisé pour [Grist](https://www.getgrist.com/) qui affiche les enregistrements d'une table regroupés par valeur de colonne, à la manière de Notion ou Airtable.

### Fonctionnalités

- **Grouper par n'importe quelle colonne** — menu déroulant dans la barre d'outils
- **Plier / déplier** chaque groupe en cliquant sur son en-tête
- **Tout plier / Tout déplier** en un clic
- **Tri des groupes** : alphabétique A→Z ou Z→A, par nombre d'enregistrements croissant ou décroissant
- **Couleur stable** par groupe (palette tournante)
- **Valeurs nulles** regroupées en *(vide)* et triées en dernier
- **Formatage des cellules** : booléens ✓/✗, nombres localisés `fr-FR`, listes
- **Options persistées** via `grist.setOption()` (colonne et tri retenus après rechargement)
- **Mode démo** intégré : données fictives affichées hors Grist pour tester le widget en standalone

### Installation

1. Dans ta table Grist, ajouter une vue → **Widget personnalisé**
2. Dans le panneau de droite, renseigner l'URL du fichier hébergé (voir ci-dessous)
3. Sélectionner l'accès **"Lire la table"**
4. Choisir la colonne de regroupement dans la barre d'outils du widget

### Hébergement

Le widget est un fichier HTML autonome, sans dépendance npm ni étape de build.  
Options d'hébergement :

- **GitHub Pages** : activer Pages sur ce dépôt, utiliser l'URL `https://<user>.github.io/grist-widget-grouped-view/widget_groupes.html`
- **Tout serveur HTTP statique** (Scalingo, Netlify, serveur WebDAV public…)

---

## 🇬🇧 English

### Overview

A Grist custom widget that displays table records grouped by any column value, similar to Notion or Airtable grouped views.

### Features

- **Group by any column** — dropdown selector in the toolbar
- **Fold / unfold** each group by clicking its header
- **Expand all / Collapse all** in one click
- **Group sort** : alphabetical A→Z or Z→A, by record count ascending or descending
- **Stable color** per group value (rotating palette)
- **Null values** collected in a *(empty)* group, sorted last
- **Cell formatting** : booleans ✓/✗, localised numbers, arrays
- **Persisted options** via `grist.setOption()` (column and sort order survive page reload)
- **Built-in demo mode** : fake records displayed when opened outside Grist

### Setup

1. In your Grist table, add a view → **Custom Widget**
2. In the right panel, enter the hosted file URL (see below)
3. Select access level **"Read table"**
4. Pick a grouping column in the widget toolbar

### Hosting

The widget is a single self-contained HTML file — no npm, no build step.  
Hosting options:

- **GitHub Pages** : enable Pages on this repo, use `https://<user>.github.io/grist-widget-grouped-view/widget_groupes.html`
- **Any static HTTP server** (Scalingo, Netlify, public WebDAV…)

---

## Fichiers / Files

| Fichier | Description |
|---|---|
| `widget_groupes.html` | Widget principal / Main widget file |

---

## Licence

MIT
