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
pourrait avoir les correspondances suivantes:

| Gamme de tensions              || Niveau      |
|--------------------------------||-------------|
| de 0 à  $$V_{DD}/3$$           || Niveau bas  |
| de $$2V_{DD}/3$$ à  $$V_{DD}$$ || Niveau haut |


Les portes logiques sont manufacturées selon différents standards
technologiques qu'on appelle familièrement des **familles
logiques**. Au sein d'une même famille, les portes respectent les
mêmes références de niveaux pour pouvoir fonctionner ensemble
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

![Porte ET à deux entrées.]({{site.baseurl}}/img/and_logique.svg "Porte ET à deux entrées")

Les portes qui réalisent des fonctions qui sont associative et
commutatives peuvent aussi se définir avec plus de deux entrées. C'est
le cas avec les fonctions ET et OU.

À trois entrées $$S =  A \cdot B \cdot C$$

![Porte ET à trois entrées.]({{site.baseurl}}/img/and3_logique.svg "Porte ET à trois entrées")


### Porte OU

À deux entrées $$S =  A + B$$

![Porte OU à deux entrées.]({{site.baseurl}}/img/or_logique.svg "Porte OU à deux entrées")


### Porte inverseur

L'opération NON qui consiste à complémenter une valeur binaire
s'effectue avec une porte appelée **inverseur**.  Il n'y a toujours
qu'une seule entrée. $$B = A^\prime$$

![Porte inverseur.]({{site.baseurl}}/img/not_logique.svg "Porte inverseur") 


### Porte NON-OU (NOR)

![Porte NOR à deux entrées.]({{site.baseurl}}/img/nor_logique.svg "Porte NOR à deux entrées")


### Porte NON-ET (NAND) et NON-OU (NOR)

Les fonctions NAND et NOR ne sont pas associatives. Par exemple, $$(x
\mbox{ NOR } y) \mbox{ NOR } z \neq x \mbox{ NOR } (y \mbox{ NOR } z)
$$. On peut néanmoins définir des versions à plusieurs entrées de ces
fonctions en ajustant la priorité d'évaluation. Pour une porte NOR à
trois entrées, on fera $$ (A + B + C)^\prime $$.

Pour une porte NAND à trois entrées, on fera $$S = (A \cdot B \cdot
C)^\prime $$.

![Porte NAND à trois entrées.]({{site.baseurl}}/img/nand3_logique.svg "NAND à trois entrées")


### Entrées inversées

On utilise souvent l'élément symbolique qui est placé à la sortie de
l'inverseur (un petit cercle) pour indiquer l'inversion d'une entrée
ou d'une sortie d'une porte. C'est le cas à la sortie des portes NAND
et NOR comme on vient de le voir. Un autre exemple est la porte NAND
de la figure suivante, où une des entrées est également
inversée. La porte évalue donc $$S =  (A^\prime \cdot B  \cdot C)^\prime $$.

![porte NAND à trois entrées dont une inversée.]({{site.baseurl}}/img/nand3_logique_invin1.svg "NAND à trois entrées dont une inversée"){:id="orgee17092"} 


### NAND et NOR, représentations équivalentes

En vertu du théorème de DeMorgan, on sait que $$(x + y)^{\prime} =
x^{\prime} y^{\prime}$$ et que $$(xy)^{\prime} = x^{\prime} +
y^{\prime}$$. On peut donc représenter les portes NAND et NOR de deux
façons équivalentes.

![Deux représentations équivalentes pour une porte NOR.]({{site.baseurl}}/img/NORequiv.svg "Deux représentations équivalentes pour une porte NOR")

![Deux représentations équivalentes pour une porte NAND.]({{site.baseurl}}/img/NANDequiv.svg "Deux représentations équivalentes pour une porte NAND")


### Porte OU-exclusif (XOR)

La porte XOR à deux entrées donne une sortie 1 seulement lorsque ses
deux entrées sont différentes. Il est possible de définir des portes
XOR à plus de deux entrées, mais il y a différentes interprétations de
ce qu'une telle porte devrait avoir comme comportement. De plus, comme
la réalisation pratique de cette fonction n'est pas aussi simple que
pour les autres fonctions, on se retrouve plus souvent qu'autrement à
devoir mettre des portes à deux entrées en cascade pour augmenter le
nombre d'entrées, ce qui rend moins intéressantes les portes XOR avec
entrées nombreuses.

$$ S= A \cdot B^\prime + A^\prime \cdot B $$ 

![Porte XOR à deux entrées.]({{site.baseurl}}/img/exor_logique.svg "Porte XOR à deux entrées")


### Porte NON-OU-exclusif ou Équivalence (XNOR)

La porte **Équivalence** produit une sortie 1 lorsque ses entrées ont
la même valeur (et sont donc équivalentes). Comme pour les portes XOR,
les portes XNOR à plus de trois entrées peuvent s'interpréter de
différentes façons.

![Porte XNOR.]({{site.baseurl}}/img/xnor_logique.svg "Porte XNOR")


## Universalité des NAND et NOR

En faisant appel uniquement à des portes de type NAND ou NOR, il est
possible de réaliser n'importe quelle fonction logique, puisqu'il est
possible de réaliser les trois opérateurs de base.

1.  Pour réaliser un inverseur, on utilise une porte NAND à une seule
    entrée (ou dont toutes les entrées sont reliées ensemble).
2.  Pour réaliser une porte ET, on fait suivre une porte NAND d'un
    inverseur.
3.  Pour réaliser une porte OU, on précède chaque entrée d'une porte
    NAND d'un inverseur.

On verra plus loin qu'il est aussi possible de réaliser
avantageusement des fonctions quelconques avec des portes NAND en
exploitant la forme **somme de produits**.
