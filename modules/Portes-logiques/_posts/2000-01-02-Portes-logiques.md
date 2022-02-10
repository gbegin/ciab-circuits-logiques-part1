---
title: Portes logiques
---

# Portes logiques

## Niveaux logiques

Une porte logique est un dispositif électronique qui implémente une
fonction logique en agissant sur des signaux électriques selon une
convention préétablie. En général, on établit des valeurs binaires en
se basant sur la tension des signaux, en définissant une
correspondance entre des gammes de tensions et les valeurs logiques 0
et 1. Par exemple, pour une tension d'alimentation $$V_{DD}$$, on
pourrait avoir les correspondances suivantes.

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">de 0 à  $$V_{DD}/3$$</td>
<td class="org-left">Niveau bas</td>
</tr>


<tr>
<td class="org-left">de $$2V_{DD}/3$$ à  $$V_{DD}$$</td>
<td class="org-left">Niveau haut</td>
</tr>
</tbody>
</table>

Les portes logiques manufacturées selon différents standards utilisent
les même références de niveaux pour pouvoir fonctionner ensemble
adéquatement.

Une porte peut comporter une ou plusieurs entrées et agit généralement
sur une seule sortie.


## Logique négative ou positive

On associe ensuite une valeur binaire à chacun des niveaux selon une
certaine convention, par exemple:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<tbody>
<tr>
<td class="org-left">Niveau bas</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">Niveau haut</td>
<td class="org-right">1</td>
</tr>
</tbody>
</table>

qui correspond à une logique positive. La convention inverse nous
donne la logique négative.

Certains signaux seront considérés comme actifs lorsque leur niveau
logique sera 0. On parlera alors de signaux **actifs bas**. La
convention implicite est généralement que les signaux sont **actifs
haut**.


## Symboles

On a défini des symboles pour représenter graphiquement les portes
logiques courantes. Dans un schéma logique, les portes sont
interconnecteées entre-elles au moyen de symboles de conducteurs
(fils) qui permettent d'acheminer les valeurs logiques d'une porte à
l'autre.


### Porte ET

À deux entrées $$S =  A \cdot B$$

![img]({{site.baseurl}}/img/and_logique.svg "Porte ET à deux entrées")

Les portes qui réalisent des fonctions qui sont associative et
commutatives peuvent aussi se définir avec plus de deux entrées. C'est
le cas avec les fonctions ET et OU.

À trois entrées $$S =  A \cdot B \cdot C$$

![img]({{site.baseurl}}/img/and3_logique.svg "Porte ET à trois entrées")


### Porte OU

À deux entrées $$S =  A + B$$

![img]({{site.baseurl}}/img/or_logique.svg "Porte OU à deux entrées")


### Porte inverseur

L'opération NON qui consiste à complémenter une valeur binaire
s'effectue avec une porte appelée **inverseur**.  Il n'y a toujours
qu'une seule entrée. $$B = A^\prime$$

![img]({{site.baseurl}}/img/not_logique.svg "Porte inverseur") 


### Porte NON-OU (NOR)

![img]({{site.baseurl}}/img/nor_logique.svg "NOR à deux entrées")


### Porte NON-ET (NAND)

Les fonctions NAND et NOR ne sont pas associatives. Par exemple, $$(x
\mbox{ NOR } y) \mbox{ NOR } z \neq x \mbox{ NOR } (y \mbox{ NOR } z)
$$. On peut néanmoins définir des versions à plusieurs entrées de ces
fonctions en ajustant la priorité d'évaluation. Pour une porte NOR à
trois entrées, on fera $$ (A + B + C)^\prime $$.

![img]({{site.baseurl}}/img/nand3_logique.svg "NAND à trois entrées")

Pour une porte NAND à trois entrées, on fera $$S = (A \cdot B \cdot
C)^\prime $$.


### Entrées inversées

On utilise souvent l'élément symbolique qui est placé à la sortie de
l'inverseur (un petit cercle) pour indiquer l'inversion d'une entrée
ou d'une sortie d'une porte. C'est le cas à la sortie des portes NAND
et NOR comme on vient de le voir. Un autre exemple est la porte NAND
de la figure [210](#orgee17092), où une des entrées est également
inversée. La porte évalue donc $$S =  (A^\prime \cdot B  \cdot C)^\prime $$.

![img]({{site.baseurl}}/img/nand3_logique_invin1.svg "NAND à trois entrées dont une inversée"){:id="orgee17092"} 


### NAND et NOR, représentations équivalentes

En vertu du théorème de DeMorgan, on sait que $$(x + y)^{\prime} =
x^{\prime} y^{\prime}$$ et que $$(xy)^{\prime} = x^{\prime} +
y^{\prime}$$. On peut donc représenter les portes NAND et NOR de deux
façons équivalentes.

![img]({{site.baseurl}}/img/NORequiv.svg "NOR représentations équivalentes")

![img]({{site.baseurl}}/img/NANDequiv.svg "NAND représentations équivalentes")


### Porte OU-exclusif (EXOR)

La porte XOR à deux entrées donne une sortie 1 seulement lorsque ses
deux entrées sont différentes. Il est possible de définir des portes
XOR à plus de deux entrées, mais il y a différentes interprétations de
ce qu'une telle porte devrait avoir comme comportement. De plus, comme
la réalisation pratique de cette fonction n'est pas aussi simple que
pour les autres fonctions, on se retrouve le plus souvent à mettre des
portes à deux entrées en cascade pour augmenter le nombre d'entrées.

$$ S= A \cdot B^\prime + A^\prime \cdot B $$ 

![img]({{site.baseurl}}/img/exor_logique.svg "Porte XOR à deux entrées")


### Porte NON-OU-exclusif ou équivalence (XNOR)

La porte équivalence produit une sortie 1 lorsque ses entrées ont la
même valeur (et sont donc équivalentes). Comme pour les portes XOR,
les portes XNOR à plus de trois entrées peuvent s'interpréter de
différentes façons.

![img]({{site.baseurl}}/img/xnor_logique.svg "Porte XNOR")


## Universalité des NAND et NOR

En faisant appel uniquement à des portes de type NAND ou NOR, il est
possible de réaliser n'importe quelle fonction logique, puisqu'il est
possible de réaliser les trois opérateurs de base.

1.  Pour réaliser un inverseur, on utilise une porte NAND à une seule
    entrée (ou dont toutes les entrées sont reliées ensemble).
2.  Pour réaliser une porte AND, on fait suivre une porte NAND d'un
    inverseur.
3.  Pour réaliser une porte OR, on précède chaque entrée d'une porte
    NAND d'un inverseur.

On verra plus loin qu'il est aussi possible de réaliser
avantageusement des fonctions quelconques avec des portes NAND en
exploitant la forme **somme de produits**.


## *Fan-out*

Le *fan-out* d'une porte logique mesure sa capacité à commander
d'autres portes reliées à sa sortie. Puisque les portes sont des
dispositifs électroniques qui doivent faire circuler un certain
courant électrique pour concrétiser les niveaux de tensions qui
définissent leurs valeurs d'entrée et de sortie, il y a une limite
pratique à la capacité d'une porte de fournir le courant nécessaire
pour faire réagir la sortie des portes qu'elle devrait commander. Le
*fan-out* mesure cette limite, en nombre de portes à commander. Si on
connecte plus d'entrées à une sortie que sa valeur de *fan-out*, la
sortie ne pourra pas atteindre le niveau de tension adéquat, et les
opérations logiques seront faussées.


## Porte tampon

La valeur binaire à la sortie d'une porte tampon est la même qu'à
l'entrée. La porte n'agit pas sur la valeur logique mais permet de
reconditionner le signal à son entrée pour le rendre, en sortie,
davantage conforme aux niveaux électriques de référence. Une porte
tampon est essentiellement utilisée pour renforcer et stabiliser le
niveau du signal. Une façon pratique de réaliser une porte tampon est
de placer deux inverseurs l'un à la suite de l'autre. L'utilisation de
portes tampon est un des moyens de s'assurer de respecter les
conditions de *fan-out*.


## Théorèmes de DeMorgan

Le complément d'une fonction $$F$$ est $$F^\prime$$ et s'obtient en
remplaçant tous les 0 par des 1 et tous les 1 par des 0 dans les
valeurs de la fonction. Par exemple, en complémentant les valeurs de
sorte dans le tableau de vérité, on effectue ce changement.

On peut aussi effectuer ce changement en appliquant les théorèmes de
DeMorgan (Théorème 5 (a) et (b) du tableau dans [Théorèmes de base]({% post_url 2000-01-02-Théorèmes-et-propriétés %}) qui
peuvent se généraliser à plus de deux variables.

