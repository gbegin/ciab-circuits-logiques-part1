---
title: Registres
---

# Registres

Un registre est un groupe de bascules activées par un même signal
d'horloge. Chaque bascule permet de stocker un bit en
mémoire. Différentes configurations d'interconnexion entre les
bascules et éventuellement des composantes combinatoires permettent de
concevoir des types de registres pouvant remplir des rôles variés.

La figure suivante montre un registre parallèle de quatre bits,
qui permet de stocker 4 valeurs binaires indépendantes. Le schéma du
bas est une représentation symbolique du registre, dans laquelle on
représente les entrées et sorties comme des vecteurs de quatre bits.

![img]({{site.baseurl}}/img/regist_4.svg "Registre parallèle à quatre bits")
*Registre parallèle à quatre bits*

### Chargement parallèle

Si on veut concevoir un registre parallèle polyvalent, on doit le
munir de la possibilité de le charger à partir des entrées ou de
maintenir les valeurs déjà mémoriser. On ajoutera donc une entrée
*charge* au registre pour contrôler ces opérations.

Comment mettre en oeuvre ce chargement/maintien demande un peu de
réflexion. Il serait possible d'agir (à la façon d'un signal *enable*
via une porte AND par exemple) sur l'entrée d'horloge des bascules
pour empêcher leur contenu d'être affectés par les entrées. Mais
alors, on briserait le principe de synchronisation qui veut que tous
les éléments d'un système soient tous commandés en même temps par une
même horloge.

La solution consiste à toujours mettre à jour le contenu des bascules: 

1.  lorsque *charge* est inactif (fonction maintien), la sortie de
    chaque bascule, réacheminée à l'entrée, est sélectionnée pour
    récrire le même contenu.
2.  Lorsque *charge* est actif (fonction chargement), c'est l'entrée
    externe qui est sélectionnée pour écrire un nouveau contenu.

La sélection se fait au moyen d'un multiplexeur deux-vers-un à
l'entrée de chaque bascule. La figure suivante montre le schéma
du registre chargeable.

![img]({{site.baseurl}}/img/reg_4_paral.svg "Registre parallèle à quatre bits chargeable")
*Registre parallèle à quatre bits chargeable*
