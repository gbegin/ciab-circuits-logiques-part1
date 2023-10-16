---
title: Théorèmes et propriétés
---

# Dualité

Les postulats ont été formulés en paires, identifiés par &spades; et
&hearts;. En interchangeant les opérateurs et les éléments identité,
on transforme un postulat de forme &spades; en un postulat de forme
&hearts;. C'est le principe de **dualité**. Ainsi, n'importe quelle
expression algébrique demeurera valide si les opérateurs et les
valeurs d'éléments identité sont interchangés.

Puisque notre algèbre ne comporte que deux éléments, les deux éléments
identité sont en fait les deux seuls éléments, 0 et 1. On obtient donc
le dual d'une expression en changeant les 0 pour des 1, les 1 pour des
0 et les ET pour des OU, les OU pour des ET.


# Théorèmes de base

Le tableau [1](#orgb76f0a7) résume les postulats et théorèmes de base de notre
algèbre. On présente en parallèle chaque version et sa version duale.

<table id="orgb76f0a7" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 1 :</span> Théorèmes de l'algèbre de Boole</caption>

<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-left">Version &spades;</th>
<th scope="col" class="org-left">Version &hearts;</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">Postulat 2</td>
<td class="org-left">$$x+0=x$$</td>
<td class="org-left">$$x \cdot 1 = x$$</td>
</tr>


<tr>
<td class="org-left">Postulat 5</td>
<td class="org-left">$$x+x^{\prime} = 1$$</td>
<td class="org-left">$$x \cdot x^{\prime} = 0$$</td>
</tr>


<tr>
<td class="org-left">Théorème 1</td>
<td class="org-left">$$x + x = x$$</td>
<td class="org-left">$$x \cdot x = x$$</td>
</tr>


<tr>
<td class="org-left">Théorème 2</td>
<td class="org-left">$$x + 1 = 1$$</td>
<td class="org-left">$$x \cdot 0 = 0$$</td>
</tr>


<tr>
<td class="org-left">Théorème 3</td>
<td class="org-left">$$(x^{\prime})^{\prime} = x$$</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">Postulat 3</td>
<td class="org-left">$$x + y = y + x$$</td>
<td class="org-left">$$xy = yx$$</td>
</tr>


<tr>
<td class="org-left">Theorème 4</td>
<td class="org-left">$$x + (y + z) = (x + y ) + z$$</td>
<td class="org-left">$$x(yz) = (xy)z$$</td>
</tr>


<tr>
<td class="org-left">Postulat 4</td>
<td class="org-left">$$x(y+z) = xy + xz$$</td>
<td class="org-left">$$x + yz = (x+y)(x+z)$$</td>
</tr>


<tr>
<td class="org-left">Théorème 5</td>
<td class="org-left">$$(x + y)^{\prime} = x^{\prime} y^{\prime}$$</td>
<td class="org-left">$$(xy)^{\prime} = x^{\prime} + y^{\prime}$$</td>
</tr>


<tr>
<td class="org-left">Théorème 6</td>
<td class="org-left">$$x + xy = x$$</td>
<td class="org-left">$$x(x+y) = x$$</td>
</tr>
</tbody>
</table>


## Autres fonctions logiques

Nous avons vu que les opérateurs logiques ET, OU et NON, qu'on peut
aussi appeler fonctions logiques, sont à la base même de la définition
de notre algèbre de Boole. Il est possible de concevoir d'autres
fonctions logiques qui vont s'avérer utiles pour la formulation, la
conception et la réalisation de systèmes logiques. Voici quelques-unes
des plus souvent utilisées.

### Fonction NON-ET (NAND)

La fonction NON-ET, souvent désignée NAND est obtenue en complémentant
la sortie d'une fonction ET: $$(x \cdot y)^\prime$$.

<table id="orge3d657b" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 2 :</span> Tableau de vérité de la fonction NON-ET</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$x$$</th>
<th scope="col" class="org-right">$$y$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">$$(x \cdot y)^\prime$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>
</tbody>
</table>


### Fonction NON-OU (NOR)

La fonction NON-OU, souvent désignée NOR est obtenue en complémentant
la sortie d'une fonction OU: $$(x + y)^\prime$$.

<table id="orgc7a557e" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 3 :</span> Tableau de vérité de la fonction NON-OU</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$x$$</th>
<th scope="col" class="org-right">$$y$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">$$(x + y)^\prime$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>
</tbody>
</table>

### Fonction OU-exclusif (XOR)

La fonction OU-exclusif, souvent désignée XOR, est obtenue par $$x
\cdot y^\prime + x^\prime \cdot y$$. La sortie est 1 seulement si
une seule des entrées est 1. On verra plus loin que cette fonction
joue un rôle important dans la formulation d'un additionneur.

<table id="orgf83558d" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 4 :</span> Tableau de vérité de la fonction OU-exclusif</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$x$$</th>
<th scope="col" class="org-right">$$y$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">$$(x \cdot y^\prime + x^\prime \cdot y)$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>
</tbody>
</table>


## Fonctions de plusieurs entrées

La plupart des fonctions logiques simples peuvent naturellement se
formuler en fonction de plus de deux entrées. Par exemple, $$a \cdot b
\cdot c$$ nous donne une fonction ET à trois entrées, et on peut
facilement imaginer des fonctions ET ou des fonctions OU avec encore
plus d'entrées.


## Expressions et fonctions binaires

Une fonction binaire peut être décrite par une expression algébrique
booléenne. Selon les valeurs des variables, la valeur de l'expression
booléenne détermine la valeur de la fonction. Par exemple, $$F_1$$ est
une fonction de trois entrées $$a, b$$ et $$c$$ définie par l'expression

$$ F_1 = a + b \cdot c^\prime $$

La priorité des opération dans les expressions algébriques est (1)
parenthèses, (2) NON, (3) ET, (4) OU.

Il est possible de construire le tableau de vérité pour $$F_1$$ en
évaluant la fonction pour les $$2^3 = 8$$ combinaisons d'entrées
possibles, comme dans le tableau [5](#orgb65522a).

<table id="orgb65522a" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 5 :</span> Fonction de trois variables</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$a$$</th>
<th scope="col" class="org-right">$$b$$</th>
<th scope="col" class="org-right">$$c$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">$$F_1$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
</tr>
</tbody>
</table>

En général, pour une fonction à $$n$$ entrées, le tableau de vérité
comportera $$2^n$$ lignes.

## Théorèmes de DeMorgan

Le complément d'une fonction $$F$$ est $$F^\prime$$ et s'obtient en
remplaçant tous les 0 par des 1 et tous les 1 par des 0 dans les
valeurs de la fonction. Par exemple, en complémentant ainsi les
valeurs dans le tableau de vérité, on effectue ce changement.

On peut aussi effectuer ce changement en appliquant les théorèmes de
DeMorgan (Théorème 5 &spades; et &hearts; du tableau dans [Théorèmes
de base]({{site.baseurl}}{% post_url
modules/Théorèmes-et-propriétés/2000-01-02-Théorèmes-et-propriétés %})
qui peuvent se généraliser à plus de deux variables.

