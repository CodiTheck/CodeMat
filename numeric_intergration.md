# Intégration numérique
![](https://img.shields.io/badge/duration-04H-yellow)
![](https://img.shields.io/badge/lastest-2024--07--12-success)
![](https://img.shields.io/badge/contact-dr.mokira%40gmail.com-blueviolet)

L'intégration numérique est un ensemble de méthodes permettant de calculer
une valeur approchée d'une intégrale définie, lorsque cette intégrale ne peut
pas être calculée de manière exacte par des méthodes analytiques (à la main).
Le principe est de découper l'intervalle d'intégration en sous-intervalles
et d'approximer la fonction à intégrer par une fonction simple
sur chaque sous-intervalle, dont on peut calculer l'intégrale.

Il existe plusieurs méthodes d'intégration numérique. Parmie elles,
nous avons :

##### Méhode des rectangles

1. On découpe l'intervalle $[a, b]$ en n sous-intervalles de même largeur $h$.
2. On remplace la fonction $f(x)$ par sa valeur au début
(méthode des rectangles à gauche), au milieu (méthode du point milieu)
ou à la fin (méthode des rectangles à droite) de chaque sous-intervalle.
3. L'intégrale est alors approximée en faisant la somme des aires
des rectangles ainsi définis.

##### Méthode des trapèzes

1. On découpe l'intervalle $[a, b]$ en n sous-intervalles de même largeur $h$.
2. Sur chaque sous-intervalle, on remplace la fonction $f(x)$
par la fonction linéaire passant par les points
$(x_i, f(x_i))$ et $(x_{i+1}, f(x_{i+1}))$.
3. L'intégrale est alors approximée en faisant la somme des aires des trapèzes
ainsi définis.

##### Méthode de Simpson

1. On découpe l'intervalle $[a, b]$ en n sous-intervalles de même largeur $h$,
avec $n$ pair.
2. Sur chaque groupe de $3$ sous-intervalles consécutifs, on remplace
la fonction $f(x)$ par le polynôme de degré 2 passant
par les points $(x_i, f(x_i))$, $(x_{i+1}, f(x_{i+1}))$
et $(x_{i+2}, f(x_{i+2}))$.
3. L'intégrale est alors approximée en faisant la somme des aires
des paraboles ainsi définies.

Ces méthodes permettent d'obtenir une valeur approchée de l'intégrale,
avec une erreur qui diminue lorsque le nombre de sous-intervalles augmente.
Le choix de la méthode dépend de la précision souhaitée et des propriétés
de la fonction à intégrer.

## Travail à faire
Vous êtes convié à implémenter le principe d'intégration numérique
de *Monte-Carlos* pour intégrer la fonction $f$ définie comme suite.

$$
f(x) = e^{-x^2}
$$

### Principe de Monte-Carlo pour l'intégration

L'objectif est de calculer numériquement l'intégrale d'une fonction $f(x)$
sur un intervalle $[a, b]$ :

$$I = \int_a^b f(x) dx$$

La méthode de *Monte-Carlo* repose sur les principes suivants :

1. On considère une variable aléatoire $X$ uniformément distribuée
sur l'intervalle $[a, b]$.
2. L'espérance mathématique de la variable aléatoire $\frac{f(X)}{(b-a)}$
est égale à l'intégrale $I$ :

$$E\left[\frac{f(X)}{b-a}\right] = \frac{1}{b-a} \int_a^b f(x) dx = \frac{I}{b-a}$$

3. On peut donc estimer l'intégrale I en calculant la moyenne empirique
de $\frac{f(X)}{(b-a)}$ sur un échantillon de N variables aléatoires
$X1, X2, ..., XN$ indépendamment tirées sur $[a, b]$ :

$$\hat{I} = (b-a) \cdot \frac{1}{N} \sum_{i=1}^N \frac{f(X_i)}{b-a}$$

Cet estimateur converge vers la valeur exacte de l'intégrale $I$
lorsque le nombre d'échantillons $N$ tend vers l'infini.
<!-- d'après la loi forte des grands nombres. -->

### Algorithme de la méthode de Monte-Carlo

Voici les étapes de l'algorithme de la méthode de *Monte-Carlo*
pour calculer l'intégrale $I$ :

1. Définir la fonction $f(x)$ à intégrer sur l'intervalle $[a, b]$.
2. Choisir un nombre N d'échantillons à générer (plus $N$ est grand,
plus la précision sera élevée).
3. Initialiser une variable somme à $0$.
4. Répéter $N$ fois :
   - Générer une variable aléatoire $X$ uniformément distribuée sur $[a, b]$.
   - Ajouter $\frac{f(X)}{(b-a)}$ à la variable somme.
5. Calculer l'estimation de l'intégrale $I$ :

$$\hat{I} = (b-a) \cdot \frac{1}{N} \cdot \text{somme}$$

### Exemple de calcul

Soit à calculer l'intégrale de la fonction $f(x) = \sin(x)$
sur l'intervalle $[0, \pi]$.

La valeur exacte de cette intégrale est :

$$I = \int_0^{\pi} \sin(x) dx = 2$$

Appliquons la méthode de Monte-Carlo pour estimer cette intégrale :

1. Définissons la fonction $f(x) = \sin(x)$ sur l'intervalle $[0, \pi]$.
2. Choisissons un nombre d'échantillons $N = 10 000$.
3. Initialisons la variable somme à $0$.
4. Répétons $10 000$ fois :
   - Générons une variable aléatoire $X$ uniformément distribuée
   sur $[0, \pi]$.
   - Ajoutons $\frac{\sin(X)}{\pi}$ à la variable somme.
5. Calculons l'estimation de l'intégrale :

$$\hat{I} = \pi \cdot \frac{1}{10000} \cdot \text{somme} = 1.9989$$

Comparons avec la valeur exacte de 2. L'erreur relative est d'environ 0,055%, ce qui est une très bonne approximation compte tenu du faible nombre d'échantillons.

### Estimation de l'erreur

L'erreur d'estimation de l'intégrale I par la méthode de *Monte-Carlo*
peut être évaluée à l'aide de la variance de l'estimateur :

$$\text{Var}(\hat{I}) = \frac{(b-a)^2}{N} \cdot \text{Var}\left(\frac{f(X)}{b-a}\right)$$

Où $Var(\frac{f(X)}{(b-a)})$ est la variance de la variable aléatoire
$\frac{f(X)}{(b-a)}$.

Un intervalle de confiance à 95% pour l'intégrale I est alors donné par :

$$\hat{I} \pm 1,96 \cdot \sqrt{\frac{(b-a)^2}{N} \cdot \text{Var}\left(\frac{f(X)}{b-a}\right)}$$

La méthode de Monte-Carlo présente l'avantage d'être indépendante
de la dimension du problème, ce qui la rend particulièrement adaptée
pour le calcul d'intégrales multidimensionnelles.

## Citations:
[1] https://www.lyceedadultes.fr/sitepedagogique/documents/math/mathTermS/11_lois_densite_loi_normale/11_integration_methode_montecarlo.pdf

[2] https://dspace.univ-adrar.edu.dz/jspui/bitstream/123456789/2142/1/Calcul%20d%E2%80%99Int%C3%A9gral%20par%20la%20M%C3%A9thode%20de%20Monte-Carlo.pdf

[3] https://www.f-legrand.fr/scidoc/docmml/numerique/montecarlo/integrales/integrales.html

[4] https://www.f-legrand.fr/scidoc/srcdoc/numerique/montecarlo/integrales/integrales-pdf.pdf

[5] https://sa4032805c7793782.jimcontent.com/download/version/1651413692/module/13755036127/name/Methode%20Monte%20Carlo.pdf
