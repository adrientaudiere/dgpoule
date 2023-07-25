
Ce site web est construit avec le logiciel libre [Zola](https://www.getzola.org). 
Ce logiciel utilise le principe de contenu séparé du style. Pour écrire du contenu, il faut aller dans le dossier `content` et écrire en format markdown. 
La mise en page et le style sont définis par les fichiers html du dossier `templates` ainsi que par les feuilles de styles. 

Ce site web utilise une action github pour reconstruire le site à chaque fois qu'un nouveau contenu est ajouté ou un style est modifié (en réalité à chaque commit).

Les nouvelles images doivent être chargées dans le dossier `/static/img/`.


## Format d'un fichier contenu

Un fichier contenu est constitué 
- d'une partie en-tête entourée de trois +  qui contient les paramètres
- d'une partie contenu à proprement dite écrite en markdown

### En-tête de paramètre

```md
+++
title = "Le pou est un parasite ? "
date = 2019-11-27
+++
```

### Contenu au format markdown

Toute la syntaxe de base peut être trouvée sur le site [original](https://daringfireball.net/projects/markdown/syntax) du format markdown. Le tableau et les éléments ci-dessous récapitulent les principales syntaxes avec des exemples spécifiquement adaptées à ce site (pour les chemins relatifs).

| Format                 | Syntaxe                                    | Exemple                                                                                                                   |
| ---------------------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------- |
| Italique               | \*Texte\*                                  | *Texte en italique*                                                                                                       |
| Gras                   | \*\*Texte\*\*                              | **Texte en gras**                                                                                                         |
| Gras italique          | \*\*\*Texte\*\*\*                          | ***Texte en gras et italique***                                                                                           |
| Lien absolu            | \[texte\](url)                             | [Je suis un lien absolu](https://adrientaudiere.github.io/dgpoule)                                                        |
| Lien relatif           | \[texte\](chemin)                          | [Je suis un lien relatif](XXXXXXXXXXXXXX)                                                                                 |
| Image (chemin absolu)  | \!\[texte alternatif\](url vers l'image)   | ![Un texte alternatif pour décrire l'image avec un lien absolu](https://adrientaudiere.github.io/dgpoule/img/logo_PP.png) |
| Image (chemin relatif) | \!\[texte alternatif\](chemin vers l'image)| ![Un texte alternatif pour décrire l'image avec un lien relatif](/img/nom_image.png)                                          |
| Citations              | \> Texte cité                              | <blockquote>Stay Hungry Stay Foolish</blockquote>                                                                         |
| Titres                 | \# Titre 1, \## Titre 2 ...)               | <h2>C'est un titre de rang 2</h2>                                                                                         |

---
---

```md
- premier élément de la liste
- deuxième élément
- troisième élément
  - Premier élément d'une sous-liste
  - Second élément de la sous-liste
```

- premier élément de la liste
- deuxième élément
- troisième élément
  - Premier élément d'une sous-liste
  - Second élément de la sous-liste

---
---

```md
1. premier élément d'une liste numérotée
1. deuxième élément
1. troisième élément
```

1. premier élément d'une liste numérotée
1. deuxième élément
1. troisième élément

---
---

```md
| Nom        | de            | colonne  |
| ------------- |:-------------:| -----:|
| la colonne 3 est      | aligné à droite | 150 |
| la colonne 2 est      | centré     |   2 |
```

| Nom        | de            | colonne  |
| ------------- |:-------------:| -----:|
| la colonne 3 est      | aligné à droite | 150 |
| la colonne 2 est      | centré     |   2 |
