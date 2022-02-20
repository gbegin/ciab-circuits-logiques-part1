---
title: Adressage
---


## Adressage

Les cellules des mémoires sont organisées en petits groupes appelés
**mots**, de façon à ce que l'on puisse accéder à chaque groupe
indépendamment. Toutes les cellules d'un mot sont lues ou écrites
ensemble.

Cet accès individuel aux mots, appelé **adressage**, est une
caractéristique de flexibilité essentielle. Le temps d'accès aux
données est le même, quel que soit l'endroit dans la mémoire où un mot
en particulier est stocké. Les mots sont généralement constitués d'un
nombre de bits multiple de huit: 8, 16 ou 32 bits sont des tailles de
mots courantes. Un groupe de huit bits est appelé **octet**.

L'adressage se fait au moyen d'un **décodeur d'adresses**, qui est
simplement un décodeur binaire tel que vu à la section  [Décodeur]({% post_url /modules/Circuits-combinatoires-typiques/2000-01-09-Décodeur %}). Le
nombre de bits d'adresse détermine la capacité (en nombre de mots) de
la mémoire: pour $$k$$ adresses, on aura $$2^k$$ mots distincts. Les
tailles de mémoire sont souvent exprimées au moyen de multiplicateurs:
K (kilo) correspondant à $$2^{10}$$, M (mega) correspondant à $$2^{20}$$
ou G (giga) correspondant à $$2^{30}$$.

![img]({{site.baseurl}}/img/memoire.png "Schéma d'une mémoire")
*Schéma d'une mémoire*

