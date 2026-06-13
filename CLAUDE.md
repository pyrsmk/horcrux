# Horcrux — Zed Theme

Ce projet est un thème Zed au format JSON, conforme au schéma `v0.2.0`.

## Structure du fichier de thème

```json
{
  "$schema": "https://zed.dev/schema/themes/v0.2.0.json",
  "name": "...",
  "author": "...",
  "themes": [ /* ThemeContent[] */ ]
}
```

| Clé       | Type     | Requis | Description                        |
|-----------|----------|--------|------------------------------------|
| `$schema` | string   | non    | URL du schéma JSON                 |
| `name`    | string   | oui    | Nom de la famille de thèmes        |
| `author`  | string   | oui    | Auteur du thème                    |
| `themes`  | array    | oui    | Liste des variantes de thème       |

---

## ThemeContent (entrée dans `themes[]`)

| Clé          | Type             | Requis | Description                        |
|--------------|------------------|--------|------------------------------------|
| `name`       | string           | oui    | Nom affiché dans l'UI              |
| `appearance` | `"dark"/"light"` | oui    | Apparence du thème                 |
| `style`      | object           | oui    | Toutes les couleurs (ThemeStyleContent) |

---

## ThemeStyleContent (`style`)

### Arrière-plan global

| Clé                    | Description                                              |
|------------------------|----------------------------------------------------------|
| `background.appearance`| `"opaque"`, `"transparent"`, ou `"blurred"` — rendu de la fenêtre |
| `background`           | Couleur de fond principale (panneaux, fenêtres)          |
| `surface.background`   | Fond de surface standard (zone de base)                  |
| `elevated_surface.background` | Fond des éléments flottants : menus contextuels, popups, dialogues |

### Bordures

| Clé                | Description                                      |
|--------------------|--------------------------------------------------|
| `border`           | Bordure principale                               |
| `border.variant`   | Bordure secondaire / atténuée                    |
| `border.focused`   | Bordure de l'élément avec le focus clavier       |
| `border.selected`  | Bordure de l'élément sélectionné                 |
| `border.transparent` | Bordure invisible (placeholder d'espacement)   |
| `border.disabled`  | Bordure des éléments non interactifs             |

### Éléments interactifs (`element.*`)

Utilisé pour les boutons, items de liste, cellules cliquables, etc.

| Clé                    | Description                          |
|------------------------|--------------------------------------|
| `element.background`   | État par défaut                      |
| `element.hover`        | Au survol                            |
| `element.active`       | En cours d'activation (clic)         |
| `element.selected`     | Sélectionné                          |
| `element.disabled`     | Désactivé                            |

### Éléments fantômes (`ghost_element.*`)

Similaire à `element`, mais pour les éléments sans fond visible à l'état normal (ex: boutons icône).

| Clé                        | Description        |
|----------------------------|--------------------|
| `ghost_element.background` | État par défaut    |
| `ghost_element.hover`      | Au survol          |
| `ghost_element.active`     | En activation      |
| `ghost_element.selected`   | Sélectionné        |
| `ghost_element.disabled`   | Désactivé          |

### Texte

| Clé                  | Description                                |
|----------------------|--------------------------------------------|
| `text`               | Couleur de texte principale                |
| `text.muted`         | Texte atténué / secondaire                 |
| `text.placeholder`   | Texte de placeholder dans les inputs       |
| `text.disabled`      | Texte des éléments désactivés              |
| `text.accent`        | Texte mis en avant / accentué              |

### Icônes

| Clé                  | Description                                |
|----------------------|--------------------------------------------|
| `icon`               | Couleur d'icône principale                 |
| `icon.muted`         | Icône atténuée                             |
| `icon.placeholder`   | Icône de placeholder                       |
| `icon.disabled`      | Icône désactivée                           |
| `icon.accent`        | Icône active / accentuée                   |

### Barres et onglets

| Clé                          | Description                          |
|------------------------------|--------------------------------------|
| `status_bar.background`      | Fond de la barre de statut (bas)     |
| `title_bar.background`       | Fond de la barre de titre (haut)     |
| `title_bar.inactive_background` | Titre quand la fenêtre est inactive |
| `toolbar.background`         | Fond de la toolbar de l'éditeur      |
| `tab_bar.background`         | Fond de la barre d'onglets           |
| `tab.active_background`      | Fond de l'onglet actif               |
| `tab.inactive_background`    | Fond des onglets inactifs            |

### Panneaux et volets

| Clé                        | Description                                      |
|----------------------------|--------------------------------------------------|
| `panel.background`         | Fond des panneaux latéraux                       |
| `panel.focused_border`     | Bordure du panneau qui a le focus                |
| `panel.indent_guide`       | Couleur des guides d'indentation dans les arbres |
| `panel.indent_guide_active`| Guide d'indentation actif                        |
| `panel.indent_guide_hover` | Guide d'indentation au survol                    |
| `pane.focused_border`      | Bordure du volet éditeur avec le focus           |
| `pane_group.border`        | Bordure entre les groupes de volets              |

### Scrollbar

| Clé                              | Description                     |
|----------------------------------|---------------------------------|
| `scrollbar.thumb.background`     | Fond du curseur de défilement   |
| `scrollbar.thumb.hover_background` | Curseur au survol             |
| `scrollbar.thumb.border`         | Bordure du curseur              |
| `scrollbar.track.background`     | Fond de la piste de défilement  |
| `scrollbar.track.border`         | Bordure de la piste             |

### Éditeur

| Clé                                        | Description                                         |
|--------------------------------------------|-----------------------------------------------------|
| `editor.background`                        | Fond de la zone d'édition                           |
| `editor.foreground`                        | Couleur de texte dans l'éditeur                     |
| `editor.gutter.background`                 | Fond du gutter (zone des numéros de ligne)          |
| `editor.subheader.background`              | Fond des sous-en-têtes (ex: diff headers)           |
| `editor.active_line.background`            | Fond de la ligne courante                           |
| `editor.highlighted_line.background`       | Fond d'une ligne mise en surbrillance               |
| `editor.line_number`                       | Couleur des numéros de ligne                        |
| `editor.active_line_number`                | Numéro de ligne de la ligne courante                |
| `editor.invisible`                         | Couleur des caractères invisibles (espaces, tabs)   |
| `editor.wrap_guide`                        | Ligne verticale de wrap                             |
| `editor.active_wrap_guide`                 | Ligne de wrap sur la ligne courante                 |
| `editor.indent_guide`                      | Guides d'indentation                                |
| `editor.indent_guide_active`               | Guide d'indentation actif                           |
| `editor.document_highlight.read_background`  | Surbrillance des occurrences en lecture           |
| `editor.document_highlight.write_background` | Surbrillance des occurrences en écriture          |
| `editor.document_highlight.bracket_background` | Surbrillance des brackets correspondants        |

### Recherche

| Clé                              | Description                              |
|----------------------------------|------------------------------------------|
| `search.match_background`        | Fond des correspondances de recherche    |
| `search.match_active_background` | Fond de la correspondance active         |

### Drag & Drop / Liens

| Clé                    | Description                           |
|------------------------|---------------------------------------|
| `drop_target.background` | Indicateur visuel de zone de dépôt  |
| `link_text.hover`      | Couleur des liens au survol           |

### États de diagnostic

Chaque état dispose de 3 variantes : couleur principale, `.background`, `.border`.

| État          | Usage                                    |
|---------------|------------------------------------------|
| `error`       | Erreurs / problèmes bloquants            |
| `warning`     | Avertissements                           |
| `info`        | Messages informatifs                     |
| `hint`        | Suggestions / hints                      |
| `success`     | Opérations réussies                      |

### États Git / fichiers

Chaque état dispose de 3 variantes : couleur principale, `.background`, `.border`.

| État          | Usage                                    |
|---------------|------------------------------------------|
| `created`     | Fichier / ligne créé(e)                  |
| `modified`    | Fichier / ligne modifié(e)               |
| `deleted`     | Fichier / ligne supprimé(e)              |
| `renamed`     | Fichier renommé                          |
| `conflict`    | Conflit de merge                         |
| `ignored`     | Fichier ignoré (gitignore)               |
| `hidden`      | Fichier caché                            |
| `unreachable` | Fichier inaccessible                     |
| `predictive`  | Contenu prédit (ex: Copilot ghost text)  |

### Accents et joueurs collaboratifs

| Clé       | Type     | Description                                                 |
|-----------|----------|-------------------------------------------------------------|
| `accents` | string[] | Tableau de couleurs d'accent (pour les décorations UI)      |
| `players` | array    | Couleurs par participant en édition collaborative           |

#### PlayerColorContent (entrée dans `players[]`)

| Clé          | Type          | Description                          |
|--------------|---------------|--------------------------------------|
| `cursor`     | string / null | Couleur du curseur du joueur         |
| `background` | string / null | Fond associé au joueur               |
| `selection`  | string / null | Couleur de sélection du joueur       |

### Terminal — couleurs ANSI

| Clé                          | Description                                |
|------------------------------|--------------------------------------------|
| `terminal.background`        | Fond du terminal                           |
| `terminal.foreground`        | Texte par défaut du terminal               |
| `terminal.bright_foreground` | Texte brillant                             |
| `terminal.dim_foreground`    | Texte atténué                              |
| `terminal.ansi.background`   | Fond ANSI (couleur 0 de fond)              |
| `terminal.ansi.black`        | Noir ANSI                                  |
| `terminal.ansi.bright_black` | Noir brillant (gris)                       |
| `terminal.ansi.dim_black`    | Noir atténué                               |
| `terminal.ansi.red`          | Rouge ANSI                                 |
| `terminal.ansi.bright_red`   | Rouge brillant                             |
| `terminal.ansi.dim_red`      | Rouge atténué                              |
| `terminal.ansi.green`        | Vert ANSI                                  |
| `terminal.ansi.bright_green` | Vert brillant                              |
| `terminal.ansi.dim_green`    | Vert atténué                               |
| `terminal.ansi.yellow`       | Jaune ANSI                                 |
| `terminal.ansi.bright_yellow`| Jaune brillant                             |
| `terminal.ansi.dim_yellow`   | Jaune atténué                              |
| `terminal.ansi.blue`         | Bleu ANSI                                  |
| `terminal.ansi.bright_blue`  | Bleu brillant                              |
| `terminal.ansi.dim_blue`     | Bleu atténué                               |
| `terminal.ansi.magenta`      | Magenta ANSI                               |
| `terminal.ansi.bright_magenta`| Magenta brillant                          |
| `terminal.ansi.dim_magenta`  | Magenta atténué                            |
| `terminal.ansi.cyan`         | Cyan ANSI                                  |
| `terminal.ansi.bright_cyan`  | Cyan brillant                              |
| `terminal.ansi.dim_cyan`     | Cyan atténué                               |
| `terminal.ansi.white`        | Blanc ANSI                                 |
| `terminal.ansi.bright_white` | Blanc brillant                             |
| `terminal.ansi.dim_white`    | Blanc atténué                              |

---

## Syntaxe (`syntax`)

Objet clé → `HighlightStyleContent`. Chaque clé correspond à un nœud Tree-sitter.

### HighlightStyleContent

| Propriété          | Type            | Valeurs possibles                        |
|--------------------|-----------------|------------------------------------------|
| `color`            | string / null   | Couleur du texte                         |
| `background_color` | string / null   | Couleur de fond                          |
| `font_style`       | string / null   | `"normal"`, `"italic"`, `"oblique"`      |
| `font_weight`      | integer / null  | 100, 200, 300, 400, 500, 600, 700, 800, 900 |

### Tokens de syntaxe disponibles

| Token                    | Rôle                                              |
|--------------------------|---------------------------------------------------|
| `attribute`              | Attributs (annotations, decorators)               |
| `boolean`                | Littéraux booléens (`true`, `false`)              |
| `comment`                | Commentaires                                      |
| `comment.doc`            | Commentaires de documentation                     |
| `constant`               | Constantes                                        |
| `constructor`            | Constructeurs / classes instanciables             |
| `emphasis`               | Emphase (Markdown *italique*)                     |
| `emphasis.strong`        | Emphase forte (Markdown **gras**)                 |
| `function`               | Fonctions et méthodes                             |
| `keyword`                | Mots-clés du langage                              |
| `label`                  | Labels (ex: étiquettes de boucle)                 |
| `link_text`              | Texte d'un lien hypertexte                        |
| `link_uri`               | URI d'un lien                                     |
| `number`                 | Littéraux numériques                              |
| `operator`               | Opérateurs (`+`, `=`, `=>`, etc.)                 |
| `property`               | Propriétés d'objets / membres                     |
| `punctuation`            | Ponctuation générale                              |
| `punctuation.bracket`    | Parenthèses, crochets, accolades                  |
| `punctuation.delimiter`  | Délimiteurs (virgules, points-virgules)           |
| `punctuation.list_marker`| Marqueurs de liste (Markdown `- `, `* `)          |
| `punctuation.special`    | Ponctuation spéciale (interpolation, etc.)        |
| `string`                 | Chaînes de caractères                             |
| `string.escape`          | Séquences d'échappement dans les strings          |
| `string.regex`           | Expressions régulières                            |
| `string.special`         | Strings spéciaux (ex: raw strings)                |
| `string.special.symbol`  | Symboles (ex: `:symbol` en Ruby)                  |
| `tag`                    | Tags HTML/XML                                     |
| `text.literal`           | Texte littéral / verbatim                         |
| `type`                   | Types, interfaces, classes                        |
| `variable`               | Variables                                         |
| `variable.special`       | Variables spéciales (`self`, `this`, etc.)        |

---

## Formats de couleur acceptés

- Hex court : `#RGB`, `#RGBA`
- Hex long : `#RRGGBB`, `#RRGGBBAA`
- `null` pour hériter ou désactiver

---

## Ressources

- Schema JSON officiel : `https://zed.dev/schema/themes/v0.2.0.json`
- Exemple de thème officiel : `https://github.com/zed-industries/zed/blob/main/assets/themes/one/one.json`
- PR de publication du schéma 0.2.0 : `https://github.com/zed-industries/zed/pull/21428`
