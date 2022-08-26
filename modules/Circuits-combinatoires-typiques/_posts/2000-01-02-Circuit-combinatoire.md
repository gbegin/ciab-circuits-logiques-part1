---
title: Circuit combinatoire
---
## Circuit combinatoire

Un circuit logique combinatoire est une combinaison de portes logiques
dont la sortie à un instant donné ne dépend que des valeurs des
entrées à cet instant. Un circuit combinatoire à $$n$$ entrées et
$$m$$ sorties peut être représenté par un schéma-bloc, dans lequel on
place généralement les entrées à gauche et les sorties à droite.

![Circuit combinatoire à n entrées et m sorties.]({{site.baseurl}}/img/circuit_comb.png "Circuit combinatoire")
*Circuit combinatoire*

Avec $$n$$ entrées, il est possible de créer $$2^n$$ combinaisons
différentes des entrées binaires. Pour chaque combinaison, le circuit
peut donner une sortie 0 ou 1. On peut donc préciser la fonction
réalisée par le circuit par un tableau de vérité comportant $$2^n$$
lignes. Comme nous avons $$m$$ sorties différentes, il y aura $$m$$
colonnes dans le tableau de vérité pour les fonctions de
sortie. Traditionnellement, on présente les entrées en ordre croissant
de combinaison binaires.

