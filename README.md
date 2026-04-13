# widget_radar.html — Graphes radar multi-catégories / Multi-category radar charts

> Widgets personnalisés pour [Grist](https://www.getgrist.com/) — [grist-widgets](https://github.com/maximelacoste/grist-widgets)

🇫🇷 [Français](#-français) · 🇬🇧 [English](#-english)

![Capture d'écran du widget radar](screenshot.png)

---

## 🇫🇷 Français

Visualise des scores sur plusieurs axes sous forme de graphes radar, directement dans Grist. Idéal pour analyser des profils, des évaluations multi-critères, ou tout jeu de données à plusieurs dimensions.

### Fonctionnalités

* **N graphes radar** (sans limite) organisés en grille 2 colonnes
* **Colonnes dynamiques** — détectées automatiquement à chaque enregistrement, compatibles avec les colonnes calculées et les `lookupOne`
* **Labels personnalisables** — renommer chaque axe directement dans le panneau de config, sans toucher aux noms de colonnes Grist
* **Configuration persistée dans `localStorage`** — aucune barre "Enregistrer" déclenchée, config isolée par table
* Par graphe : titre, emoji, couleur du contour, couleur de la grille, échelle max
* Ajout, suppression et réorganisation des graphes depuis le panneau ⚙️
* **Mode présentation** — ouvre `presenter.html` dans un nouvel onglet avec navigation clavier et plein écran
* **Bilingue** FR / EN — détection automatique via `navigator.language`
* **Accessible** — ARIA, navigation clavier, focus visible

### Installation

#### 1. Héberger les fichiers

Les deux fichiers `widget_radar.html` et `presenter.html` doivent être hébergés **au même endroit** depuis un serveur autorisant l'intégration en iframe.

[Netlify](https://netlify.com) fonctionne parfaitement et est gratuit :
1. Télécharge `widget_radar.html` et `presenter.html`
2. **Add new site → Deploy manually** → glisse-dépose un dossier contenant les deux fichiers
3. Netlify fournit une URL du type `https://ton-site.netlify.app/widget_radar.html`

> ℹ️ GitHub Pages fonctionne aussi si ton dépôt est public et que Grist est configuré pour autoriser cette source.

#### 2. Ajouter le widget dans Grist

1. Ajouter un **widget personnalisé** dans ton document Grist
2. Coller l'URL du fichier hébergé
3. Configurer **"Sélectionner par"** sur ta table de données
4. Régler l'**accès aux données** sur **"Lire la table"**
5. Cliquer sur un enregistrement → les graphes s'affichent

#### 3. Configurer les graphes

Cliquer sur **⚙️** en haut à droite pour ouvrir le panneau de configuration.

Pour chaque graphe :

| Champ | Description |
|---|---|
| Emoji + Titre | Libellé du graphe |
| Contour | Couleur de l'étoile |
| Repère | Couleur de la grille de fond |
| Max | Valeur maximale de l'échelle |
| Colonnes | Cases à cocher + champ libellé pour renommer chaque axe |

#### 4. Mode présentation

Cliquer sur **▶ Présentation** pour ouvrir `presenter.html` dans un nouvel onglet :
- Navigation **← →** au clavier entre les enregistrements
- Bouton **plein écran** natif
- Compteur de position (**3 / 7**)

### Structure des données

Une ligne = un enregistrement. Les scores sont dans des colonnes numériques (directes ou via formule / `lookupOne`) :

| Colonne | Description |
|---|---|
| `lang_comprehension` | Score de compréhension |
| `math_calcul` | Score de calcul |
| `compor_attention` | Score d'attention |
| … | … |

Les noms de colonnes sont entièrement configurables depuis le panneau ⚙️.

Un fichier CSV de démonstration (`eleves_scores.csv`) est disponible pour tester rapidement.

### Fichiers

| Fichier | Rôle |
|---|---|
| `widget_radar.html` | Widget à intégrer dans Grist |
| `presenter.html` | Page de présentation plein écran |
| `eleves_scores.csv` | Table de démonstration |
| `screenshot.png` | Capture d'écran |

---

## 🇬🇧 English

Displays scores on multiple axes as radar (spider) charts, directly inside Grist. Ideal for student profiles, multi-criteria assessments, or any multi-dimensional dataset.

### Features

* **N radar charts** (unlimited) arranged in a 2-column grid
* **Dynamic columns** — auto-detected on every record, compatible with formula columns and `lookupOne`
* **Custom labels** — rename each axis directly in the config panel, without changing Grist column names
* **localStorage persistence** — no Grist "Save layout" bar, config scoped per table
* Per chart: title, emoji, outline colour, grid colour, max scale
* Add, remove and reorder charts from the ⚙️ panel
* **Presentation mode** — opens `presenter.html` in a new tab with keyboard navigation and full-screen support
* **Bilingual** FR / EN — auto-detected via `navigator.language`
* **Accessible** — ARIA, keyboard navigation, visible focus

### Installation

#### 1. Host the files

Both `widget_radar.html` and `presenter.html` must be hosted **at the same location** on a server that allows iframe embedding.

[Netlify](https://netlify.com) works perfectly and is free:
1. Download `widget_radar.html` and `presenter.html`
2. **Add new site → Deploy manually** → drag-and-drop a folder with both files
3. Netlify gives you a URL like `https://your-site.netlify.app/widget_radar.html`

> ℹ️ GitHub Pages also works if your repo is public and Grist is configured to allow that source.

#### 2. Add the widget in Grist

1. Add a **Custom Widget** in your Grist document
2. Paste the hosted file URL
3. Set **"Select by"** to your data table
4. Set **Data access** to **"Read table"**
5. Click a record → charts appear

#### 3. Configure the charts

Click **⚙️** at the top right to open the configuration panel.

Per chart:

| Field | Description |
|---|---|
| Emoji + Title | Chart label |
| Outline | Star colour |
| Grid | Background grid colour |
| Max | Maximum scale value |
| Columns | Checkboxes + label input to rename each axis |

#### 4. Presentation mode

Click **▶ Present** to open `presenter.html` in a new tab:
- **← →** keyboard navigation between records
- Native **full-screen** button
- Position counter (**3 / 7**)

### Expected data structure

One row = one record. Scores are in numeric columns (direct, formula, or `lookupOne`):

| Column | Description |
|---|---|
| `lang_comprehension` | Comprehension score |
| `math_calcul` | Calculation score |
| `compor_attention` | Attention score |
| … | … |

Column names are fully configurable from the ⚙️ panel.

A demo CSV file (`eleves_scores.csv`) is available for quick testing.

### Files

| File | Purpose |
|---|---|
| `widget_radar.html` | Widget to embed in Grist |
| `presenter.html` | Full-screen presentation page |
| `eleves_scores.csv` | Demo table |
| `screenshot.png` | Screenshot |

---

## Licence / License

[MIT](../LICENSE)
