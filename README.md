
Ce site web est construit avec le logiciel libre [Zola](https://www.getzola.org). 
Ce logiciel utilise le principe de contenu séparé du style. Pour écrire du contenu, il faut aller dans le dossier `content` et écrire en format markdown. 
La mise en page et le style sont définis par les fichiers html du dossier `templates` ainsi que par les feuilles de styles. 

Ce site web utilise une action github pour reconstruire le site à chaque fois qu'un nouveau contenu est ajouté ou un style est modifié (en réalité à chaque action `push`).

## Gestion des images

Les nouvelles images doivent être chargées dans le dossier `/static/img/`. Pour limiter la taille des images, il est conseillé de convertir les images en format *webp* à l'aide de l'éditeur en ligne [squoosh](https://squoosh.app/editor).

Pour les images dans les slides, cf la [section](#img_html) sur les images dans le contenu HTML

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
| Lien relatif           | \[texte\](chemin)                          | [Je suis un lien relatif](/connaissance)                                                                                 |
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


### Contenu au format html

Quelques rares cas nécessitent un peu de language HTML dans le contenu.
Attention les lignes vides sont importantes.

### Faire un commentaire 

Pour écrire un texte qui ne sera pas visible (par ex. pour annoter un endroit où l'on voudrait rajouter une image), il faut utiliser la notation suivante :

```md
<!-- Idéalement, une figure montrant un acarien grimpant sur une patte serait chouette (mais pas indispensable) -->
```

#### Image qui prend toute la largeur avec une légende. {#img_html}

```md
<div class="img_largeur_max"">

![Description de l'image](/img/nom_de_l'image.png)

Légende

</div>
```

On peux changer la valeur de pourcentage du paramètre `width` du *style* pour avoir une image moins large. Par exemple pour avoir une image à 60% de la largeur on écrit :

```md
<div class="img_largeur_max" style="width:60%">

![Description de l'image](/img/nom_de_l'image.png)

Légende

</div>
```

#### Style pour le "En savoir plus des connaissances"

```md

<details>
    <summary>En savoir plus</summary>

Du texte d'explication.

### Sources scientifiques

- Dupont et Dupond 2022
-  Roy, L, Taudière, A, Papaïx, J, et al. Evaluating the link between predation and pest control services in the mite world. Ecol Evol. 2020; 10: 9968 - 9980. https://doi.org/10.1002/ece3.6655

</details>
```