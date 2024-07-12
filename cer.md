# Character Error Rate (CER)
![](https://img.shields.io/badge/duration-04H-yellow)
![](https://img.shields.io/badge/lastest-2024--07--12-success)
![](https://img.shields.io/badge/contact-dr.mokira%40gmail.com-blueviolet)

Le CER (Character Error Rate) est une métrique utilisée pour évaluer
la performance des systèmes de reconnaissance automatique
de la parole (ASR) et de traduction
automatique en comparant la sortie générée par le modèle à une référence
correcte. Le CER est similaire au WER (Word Error Rate) mais fonctionne
au niveau
des caractères plutôt qu’au niveau des mots, ce qui le rend particulièrement
utile pour les langues avec une morphologie complexe ou lorsque les erreurs
de transcription se produisent à un niveau plus granulaire.

### Calcul du CER

Le CER est calculé en utilisant l'algorithme de distance de Levenshtein,
qui mesure le nombre minimal d'opérations nécessaires pour transformer
une chaîne de caractères en une autre. Les opérations possibles sont :

- **Insertion** : Ajouter un caractère.
- **Suppression** : Supprimer un caractère.
- **Substitution** : Remplacer un caractère par un autre.

Voici l’expression pour calculer le CER :

$$
CER = \frac{I + D + S}{N}
$$

où :

- $I$ est le nombre d'insertions;
- $D$ est le nombre de suppressions;
- $S$ est le nombre de substitutions;
- $N$ est le nombre de caractères dans la référence.

### Exemple de Calcul du CER

Supposons que nous avons une référence et une hypothèse comme suit :
- Référence : "chat"
- Hypothèse : "chzt"

Pour calculer le CER :
1. Alignez les deux chaînes en utilisant la distance de Levenshtein :
   - Référence : "chat"
   - Hypothèse : "chzt"

   Les opérations nécessaires sont :
   - Substitution de 'a' par 'z' (1 substitution).

2. Calculons le CER :
   - Nombre de substitutions ($S$) = 1
   - Nombre d'insertions ($I$) = 0
   - Nombre de suppressions ($D$) = 0
   - Nombre de caractères dans la référence ($N$) = 4

$$
CER = \frac{1 + 0 + 0}{4} = 0.25
$$

###### Utilité du CER
Le taux d'erreur au niveau des caractères (Character Error Rate ou CER)
est utilisée pour évaluer la qualité des sorties de systèmes de reconnaissance 
automatique de la parole (RAP) ou de systèmes d'OCR. 

### Avantages et Limites

#### Avantages :
- **Granularité Fine** : Capte les erreurs au niveau des caractères,
ce qui est utile pour les langues à morphologie riche.
- **Simplicité** : Relativement simple à calculer et à interpréter.

#### Limites :
- **Sensibilité** : Peut être trop sensible aux petites erreurs pour des 
applications où la sémantique globale est plus importante que la précision
de chaque caractère.
- **Pas de Sens du Contexte** : Ne tient pas compte du contexte
ou de la structure grammaticale, seulement des erreurs de surface.

En résumé, le CER est une métrique efficace pour évaluer la qualité
des transcriptions ou des traductions au niveau des caractères,
particulièrement utile pour des tâches où les erreurs de caractère
peuvent avoir un impact significatif.

## Travail à faire
Implémenter l'algorithme du **CER** dans un langage compilé (C/C++, ou autre)
et dans un autre interprêté (Python, JavaScript, ou autre).
