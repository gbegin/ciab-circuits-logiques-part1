---
title: Mémoires mortes
---

## Mémoires mortes

Dans son mode d'utilisation normal, une mémoire morte peut seulement
être lue. Il n'est donc pas nécessaire de préciser l'opération qui
sera effectuée. Il y aura donc des entrées pour les adresses et un
signal de contrôle de type *CS*.

La figure suivante montre l'essentiel d'une mémoire ROM de
16 mots de 4 bits. Un décodeur d'adresse permet de sélectionner quel
mot sera lu, et la sortie est disponible sur les lignes $$A_3, \ldots,
A_0$$. 

![img]({{site.baseurl}}/img/proto_rom1_prog.svg "Modèle d'une mémoire ROM")
*Modèle d'une mémoire ROM*

Pour simplifier la représentation de genre de configuration, on
utilise une schématisation symbolique compacte pour les portes OU de
sortie, dans laquelle chacune des 16 lignes horizontales représente en
fait 16 entrées d'une porte OU. La présence d'une croix à
l'intersection d'une ligne horizontale et d'une ligne verticale
signifie que le signal de la ligne horizontale est connecté à une des
entrées de la porte.  Avec cette schématisation, on peut voir que les
deux premiers mots stockés dans la mémoire illustrée dans l'exemple
seraient 0101 et 1101. La même schématisation compacte est aussi
employée pour des portes ET.

Cette relativement petite mémoire comporte ainsi 64 intersections
programmables, permettant de définir la valeur des 16 mots de mémoire
de 8 bits chacun.


### Implémentation de fonctions combinatoires

Comme on l'a vu dans la section [Décodeur]({{site.baseurl}}{% post_url modules/Circuits-combinatoires-typiques/2000-01-09-Décodeur %}), un décodeur permet de
générer les $$2^k$$ minterms possibles avec ses $$k$$
entrées. Regrouper avec une porte OU les minterms d'une
fonction permet d'implémenter cette fonction. Une mémoire ROM permet
de faire exactement cela sans avoir rien à ajouter, car elle est munie
d'un décodeur d'entrées et la porte OU de sortie fait déjà partie de
la ROM. On peut donc interpréter le fonctionnement d'une mémoire ROM
de $$k$$ bits d'adresse et avec des mots de taille $$m$$ comme un
dispositif qui permet, pour les entrées qui sont ses adresses, de
mettre en oeuvre $$m$$ fonctions combinatoires différentes (une par
bit de mot) de $$k$$ entrées.

Par exemple, la sortie $$A_2$$ de la mémoire de la figure
précédente implémente la fonction $$ A_2 = \sum (0,1,4,8) $$
exprimée en somme de minterms.


### Tableau de correspondance

Cette approche qui consiste à réaliser une fonction logique
combinatoire au moyen d'une mémoire qui spécifie, pour chaque
combinaison d'entrée possible, une valeur de sortie, est largement
utilisée dans les composants programmables. On parle alors de tableau
de correspondance (en anglais, *LookUp Table*, (LUT)). Il s'agit ni
plus ni moins que de stocker en mémoire le tableau de vérité de la
fonction à réaliser. Dans les composants programmables, on utilise
plutôt des mémoires RAM pour les tableaux de correspondance, afin que
la configuration des fonctions puisse être changée selon
l'application.

### Catégories de mémoires ROM

On distingue quatre grandes approches technologiques pour réaliser des
mémoires mortes. Leurs usages typiques sont surtout déterminés par la
façon de les configurer (on dit couramment *programmer*, même s'il
s'agit d'un intervention au niveau du matériel).

Dans la **programmation par masque**, la mémoire est programmée lors de
la fabrication de la puce. Le fabricant se base sur un tableau de
vérité fourni par le client pour établir des connexions qui seront
implémentées (ou pas) dans le procédé de fabrication via des masques
qui empêchent la déposition de matériau conducteur sur les couches de
la puce.  Cette approche convient à la production de masse à grand
volume.

Dans la **programmation sur mesure**, on utilise un type de mémoire qui
comporte initialement des connexions entre toutes les sorties du
décodeur et toutes les entrées des portes OU de sortie (la mémoire en
configuration initiale comporte des 1 partout). La programmation, qui
peut se faire chez le développeur au moyen d'un dispositif programmeur
spécialement conçu à cette fin, consiste à supprimer les connexions
qui ne sont pas nécessaires en envoyant des impulsions à forte tension
pour faire fondre les fusibles de connexions spécifiques. Un fusible
fondu (pas de connexion) correspondant un un bit 0 dans la
mémoire. Cette programmation est bien entendu irréversible: impossible
de reconnecter une fois que le fusible est fondu.

Avec un **PROM** (pour *Programmable ROM*), il est possible d'effacer la
configuration dans son ensemble en soumettant la puce à une lumière
ultraviolet pendant un certain temps. Ce bombardement énergétique
permet de décharger les grilles flottantes des dispositifs qui
implémente les connexions. La mémoire PROM peut être reconfigurée de
nouveau.

Avec la **programmation électrique**, il est possible de reconfigurer
l'ensemble d'une mémoire dite EEPROM (*Electrically Erasable PROM*)
en la soumettant à un signal électrique d'effacement. 

Les ROM à **programmation *flash*** sont semblables aux EEPROM, mais la
reconfiguration peut se faire adresse par adresse.  Il est notamment
possible de reconfigurer une mémoire sans la retirer de son circuit.
Fonctionnellement, ces mémoires sont à mi-chemin entre la mémoire RAM
et la mémoire sur disque. Les mémoires *flash* tendent d'ailleurs de
plus en plus à remplacer ce dernier type dans les systèmes portables:
téléphones, ordinateurs portables, etc.

