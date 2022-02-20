---
title: Chronogrammes
---

### Chronogrammes

La figure [785](#orgd3f1b4d) présente un chronogramme qui décrit
l'opération d'écriture dans une mémoire RAM. Les valeurs d'adresse
sont d'abord présentée aux entrées d'adressage.  Le signal L/not E
est amené au niveau bas, en même temps que le signal *cs* est activé
(au niveau bas). Après un court délai, les données sont mises sur le
bus de données et seront écrites dans la mémoire. On peut voir que les
llignes du bus de données sont en mode **haute impédance** lorsque le bus
est inactif (situation représentée symboliquement sur l'illustration
par un signal situé entre les niveaux 0 et 1).

![img]({{site.baseurl}}/img/chron_ram_ecriture.svg "Mémoire RAM, chronogramme pour l'écriture")
*Mémoire RAM, chronogramme pour l'écriture*

La figure [787](#org66401d9) présente un chronogramme qui décrit
l'opération de lecture d'une mémoire RAM. Les valeurs d'adresse sont
d'abord présentée aux entrées d'adressage.  Le signal *L / not E* est
maintenu au niveau élevé en même temps que le signal *CS* est activé
(au niveau bas). Après un court délai, les données sont disponibles sur
le bus de données.

![img]({{site.baseurl}}/img/chron_ram_lecture.svg "Mémoire RAM, chronogramme pour la lecture")
*Mémoire RAM, chronogramme pour la lecture*

La cellule de base d'une mémoire RAM qui permet de stocker un bit est
illustrée à la figure [789](#org7ec9f62). Elle est construite autour d'un
loquet SR et de portes logiques pour le contrôle. Une mémoire complète
de $$m$$ mots de taille $$n$$ bits sera constituée d'une matrice de
format $$m \times n$$ de telles cellules, avec un décodeur d'adresses
pour sélectionner quel mot sera affecté par l'opération choisie.

![img]({{site.baseurl}}/img/cell_ram.svg "Cellule mémoire RAM")
*Cellule mémoire RAM*
