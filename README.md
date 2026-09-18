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

### Installation

1. Dans ta table Grist, ajouter une vue → **Widget personnalisé**
2. Dans le panneau de droite, renseigner l'URL du fichier hébergé (voir ci-dessous)
3. Sélectionner l'accès **« Lire la table »**
4. Choisir la colonne de regroupement dans la barre d'outils du widget

### Hébergement

Le widget est un fichier HTML autonome, sans dépendance npm ni étape de build.
Options d'hébergement :

- **GitHub Pages** : activer Pages sur ce dépôt, utiliser l'URL `https://<user>.github.io/grist-widget-grouped-view/widget_groupes.html`
- **Tout serveur HTTP statique** (Scalingo, Netlify, serveur WebDAV public…)

Le widget est chargé par le navigateur, pas par le serveur Grist : il doit donc être servi en **HTTPS**, sans quoi le navigateur le bloquera comme contenu mixte. Il est également recommandé de l'héberger sur un **domaine distinct** de celui de l'instance Grist, afin de préserver l'isolation d'origine du navigateur.

### Persistance des réglages

La colonne de regroupement, le tri, les couleurs et la hauteur maximale sont enregistrés dans la configuration de la vue via `grist.setOption()`.

Comme pour les tris et les filtres natifs de Grist, ces changements restent en attente jusqu'à ce que vous cliquiez sur **Enregistrer** dans la barre d'outils. Sans cette validation, ils sont perdus au rechargement de la page.

Les personnes en lecture seule voient la configuration enregistrée par l'éditeur et ne peuvent pas la modifier.

### Accessibilité

Le widget vise le niveau AA des WCAG 2.2. Un widget n'ayant pas de déclaration d'accessibilité propre, c'est le service qui l'intègre qui reste soumis au RGAA.

Points traités :

- accordéon utilisable au clavier, avec `aria-expanded` et `aria-controls` ;
- contenu d'un groupe plié retiré de la restitution des lecteurs d'écran ;
- zones défilables atteignables au clavier ;
- contrastes conformes (4,5:1 minimum) sur l'ensemble des fonds utilisés ;
- cibles d'interaction d'au moins 24 × 24 px ;
- tableaux avec `<caption>` et en-têtes de colonnes explicites ;
- attribut `lang` aligné sur la langue d'interface détectée ;
- `prefers-reduced-motion` pris en compte ;
- valeurs tronquées accessibles via l'attribut `title` ;
- comportement au zoom 200 % vérifié (WCAG 1.4.10).

Points non vérifiés à ce jour :

- restitution par lecteur d'écran (VoiceOver, NVDA, JAWS) ;
- certains textes secondaires sont affichés en 10–11 px, choix de densité assumé, sans incidence sur le zoom.

Les retours sur ces points sont bienvenus.

### Sécurité

- Le widget demande le niveau d'accès minimal, « Lire la table ».
- Les valeurs de cellules et les noms de colonnes sont échappés avant insertion.
- Les couleurs stockées dans les options sont strictement validées (`#rrggbb`).
- Aucune dépendance externe hors `grist-plugin-api.js`, aucun appel réseau, aucun stockage navigateur.

Pour signaler un problème de sécurité, ouvrez une issue ou contactez le mainteneur directement.

---

## 🇬🇧 English

### Overview

A Grist custom widget that displays table records grouped by any column value, similar to Notion or Airtable grouped views.

### Features

- **Group by any column** — dropdown selector in the toolbar
- **Fold / unfold** each group by clicking its header
- **Expand all / Collapse all** in one click
- **Group sort**: alphabetical A→Z or Z→A, by record count ascending or descending
- **Stable color** per group value (rotating palette)
- **Null values** collected in an *(empty)* group, sorted last
- **Cell formatting**: booleans ✓/✗, localised numbers, arrays
- **Persisted options** via `grist.setOption()` (column and sort order survive page reload)

### Setup

1. In your Grist table, add a view → **Custom Widget**
2. In the right panel, enter the hosted file URL (see below)
3. Select access level **"Read table"**
4. Pick a grouping column in the widget toolbar

### Hosting

The widget is a single self-contained HTML file — no npm, no build step.
Hosting options:

- **GitHub Pages**: enable Pages on this repo, use `https://<user>.github.io/grist-widget-grouped-view/widget_groupes.html`
- **Any static HTTP server** (Scalingo, Netlify, public WebDAV…)

The widget is loaded by the browser, not by the Grist server, so it must be served over **HTTPS** — otherwise the browser blocks it as mixed content. Hosting it on a **separate domain** from the Grist instance is also recommended, to preserve browser origin isolation.

### Saving settings

The grouping column, sort order, colors and maximum height are stored in the view configuration through `grist.setOption()`.

As with Grist's built-in sorts and filters, these changes stay pending until you click **Save** in the toolbar. Without that confirmation, they are lost on reload.

Read-only users see the configuration saved by the editor and cannot change it.

### Accessibility

The widget targets WCAG 2.2 level AA. A widget has no accessibility statement of its own: the service embedding it remains the one bound by accessibility regulations.

Addressed:

- keyboard-operable accordion, with `aria-expanded` and `aria-controls`;
- collapsed group content removed from screen reader output;
- scrollable regions reachable by keyboard;
- contrast ratios of at least 4.5:1 against every background in use;
- interaction targets of at least 24 × 24 px;
- tables with `<caption>` and explicit column headers;
- `lang` attribute matching the detected interface language;
- `prefers-reduced-motion` honoured;
- truncated values exposed through the `title` attribute;
- 200 % zoom behaviour verified (WCAG 1.4.10).

Not verified yet:

- screen reader output (VoiceOver, NVDA, JAWS);
- some secondary text renders at 10–11 px, a deliberate density choice that does not affect zoom.

Feedback on these points is welcome.

### Security

- The widget requests the minimum access level, "Read table".
- Cell values and column names are escaped before insertion.
- Colors stored in widget options are strictly validated (`#rrggbb`).
- No external dependency beyond `grist-plugin-api.js`, no network calls, no browser storage.

To report a security issue, open an issue or contact the maintainer directly.

---

## Fichiers / Files

| Fichier               | Description                         |
| --------------------- | ----------------------------------- |
| `widget_groupes.html` | Widget principal / Main widget file |

---

## Licence

MIT
