# One Hot Encoding
![](https://img.shields.io/badge/duration-02H-yellow)
![](https://img.shields.io/badge/lastest-2024--07--12-success)
![](https://img.shields.io/badge/contact-dr.mokira%40gmail.com-blueviolet)

Le one hot encoding (Encodage à chaud) est une technique utilisée
pour représenter des variables
catégorielles sous forme numérique, afin de pouvoir les utiliser
dans des algorithmes d'apprentissage automatique.

Le principe est de créer autant de colonnes binaires que de catégories
possibles pour une variable donnée. Chaque colonne correspond à une catégorie.
Pour chaque observation, la colonne correspondant à sa catégorie prend
la valeur $1$, tandis que les autres colonnes prennent la valeur $0$.

Par exemple, pour une variable "couleur" avec $3$ catégories
(rouge, vert, bleu), on créera $3$ colonnes binaires. Une observation
de couleur rouge sera encodée `[1, 0, 0]`, une observation verte `[0, 1, 0]`,
et une bleue `[0, 0, 1]`.

###### Utilité du one hot encoding ?
La plupart des algorithmes d'apprentissage automatique ne peuvent pas traiter 
directement des variables catégorielles. Ils s'attendent à des entrées
numériques. 

Assigner des valeurs numériques arbitraires aux catégories
(par exemple 0, 1, 2) n'est pas une bonne solution car cela introduirait
une notion d'ordre entre les catégories qui n'existe pas forcément. De plus, 
certains algorithmes comme la régression linéaire pourraient être biaisés
par ces valeurs.

Le one hot encoding permet de représenter les catégories de manière neutre,
sans introduire de relation d'ordre artificielle. Chaque catégorie
est représentée par un vecteur binaire orthogonal aux autres.

Par exemple, s'il s'agit d'un problème de reconnaissance d'un animal
sur des images entre Chien, Chat, Mouton et Aigle, alors en utilisant
le principe d'encodage à chaud, nous avons :

| Catégorie | Indexe    | Code One Hot   |
|-----------|-----------|----------------|
|  Chien    |   $0$     | `[1, 0, 0, 0]` |
|  Chat     |   $1$     | `[0, 1, 0, 0]` |
|  Mouton   |   $2$     | `[0, 0, 1, 0]` |
|  Aigle    |   $3$     | `[0, 0, 0, 1]` |


## Travail à faire
Implémenter la méthode du **One Hot Encoding**.