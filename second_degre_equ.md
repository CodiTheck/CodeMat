# Equation du 2nd degré
![](https://img.shields.io/badge/duration-03H-yellow)
![](https://img.shields.io/badge/lastest-2024--05--16-success)
![](https://img.shields.io/badge/contact-dr.mokira%40gmail.com-blueviolet)

Écrire un programme permettant de calculer les solutions d'une **équation
du second degré**. Je te rappel qu'une équation du second degré est
sous la forme :

$$
a x^2 + b x + c = 0
$$

avec les réels $a$, $b$ et $c$ les coéfficients de l'équation et
$a \ne 0$.

Exemple d'équation du second degré :
- $3 x^2 - 4 = 0$, 
- $x^2 + 10 x - 9 = 0$,
- $6x^2 = 0$,
- $-x^2 + 2 x = 0$ .

> Par contre $3x - 9 = 0$ ou $3 = 0$ ne sont pas
des équations du second degré.

## Fonctionnement
Le programme demande à l'utilisateur de saisir les coéfficients $a$, $b$ et $c$
ensuite le programme affiche une des trois (03) sorties suivantes :

- Lorsque l'équation n'admet pas de solution, alors on affiche :

```
Pas de solutions !
```

- Lorsque l'équation admet une solution double (identiques) comme par exemple
$x_0 = 2.38$, alors on affiche :

```
Solution double : x0 = 2.38
```

- Lorsque l'équation admet deux solutions distinctes $x_1$ et $x_2$
comme par exemple $x_1 = 10$ et $x_2 = -9$, alors on affiche :

```
Deux solution distinctes x1 = 10 et x2 = -9
```

> **NOTE** : Le programme doit prendre en compte tous les cas d'erreurs
dans son traitement.

