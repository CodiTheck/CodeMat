# Valid Date
![](https://img.shields.io/badge/duration-03H-yellow)
![](https://img.shields.io/badge/lastest-2024--03--18-success)
![](https://img.shields.io/badge/contact-dr.mokira%40gmail.com-blueviolet)

Écris une **fonction** permettant de vérifier la validité d'une date reçue
en argument. La fonction retourne `true` si les valeurs de jour, mois, année
(jj/mm/aaaa) forme une date valide, sinon, elle retourne `false`.

> **NOTE**: N'oublis pas de traiter le cas des années bixessiles. Ces dernières
sont soit multiples de 4 ou soit multiples de 100 et 400. Par exemple 2024,
2004, 2020, etc. Dans ces années, le mois de Février se termine par 29. Alors
que dans les autres années (non-bixessiles), le mois de Février compte
28 jours.

Pour tester ta fonction de vérification de date,

- tu vas écrire un programme dans la fonction principale `main()` dans lequel
tu feras l'acquisition du numéro de jour, du numéro de mois et de l'années
de l'utilisateur.
- Ensuite, tu vas appeller ta fonction de vérification de date en lui passant
les valeurs saisies par l'utilisateur.
- Et enfin, tu afficheras le message suivant,

```
La date que vous aviez saisie est valide.
```

si la fonction renvoie `true`,

ou le message suivant,

```
La date que vous aviez saisie n'est pas valide.
```

si la fonction renvoie `false`.

Exemple :

- Pour **01/01/1990** : La date que vous aviez saisie est valide.
- Pour **31/10/2022** : La date que vous aviez saisie n'est pas valide.
- Pour **11/08/2044** : La date que vous aviez saisie est valide.
- Pour **29/02/2022** : La date que vous aviez saisie n'est pas valide.
