---
title: Additionneur binaire
---

## Circuits logiques combinatoires classiques

Nous allons maintenant nous intéresser à un certain nombre de
fonctions typiques que l'on rencontre fréquemment en circuits
logiques. Ce sera aussi l'occasion de mettre en pratique les approches
de conception que nous avons vues.


## Additionneur binaire

Une des opérations binaires les plus utilisées est l'addition (et la
soustraction). Nous avons présenté à la section  [Compléments]({{site.baseurl}}{% post_url modules/Systèmes-de-numération/2000-01-05-Compléments %}) le tableau de vérité pour un additionneur binaire dont les
entrées sont $$a_{i}$$ et $$b_{i}$$, les bits des nombres à
additionner et $$r_{i-1}$$, la retenue provenant de la position
$$i-1$$. En sortie, on a la somme $$S_{i}$$ et la retenue
$$R_{i}$$. Notez bien que pour distinguer la retenue d'entrée de la
retenue de sortie, nous utilisons un symbole minuscule, $$r_{i-1}$$,
pour l'entrée et un symbole majuscule, $$R_{i}$$, pour la sortie.

![img]({{site.baseurl}}/img/additionneur.png "Additionneur complet")
*Additionneur complet*

<table id="org18af8cd" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 2 :</span> Tableau de vérité pour l'additionneur binaire</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$a_{i}$$</th>
<th scope="col" class="org-right">$$b_{i}$$</th>
<th scope="col" class="org-right">$$r_{i-1}$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">$$R_{i}$$</th>
<th scope="col" class="org-right">$$S_{i}$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
</tr>
</tbody>
</table>


### Demi-additionneur

Un circuit logique qui effectue l'addition de deux bits est appelé un
demi-additionneur. Mais ce qu'il nous faut vraiment, c'est un
additionneur complet, c'est-à-dire, un circuit qui fait l’addition de
trois bits, puisqu'il faudra pouvoir tenir compte de la retenue du
niveau précédent pour effectuer l'addition sur un niveau. Il est
possible d'implémenter l'additionneur complet avec deux
demi-additionneurs.

<table id="org3332911" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 3 :</span> Tableau de vérité pour un demi-additionneur</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$a_{i}$$</th>
<th scope="col" class="org-right">$$b_{i}$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">$$R_{i}$$</th>
<th scope="col" class="org-right">$$S_{i}$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
</tr>
</tbody>
</table>

À partir du tableau de vérité, on peut trouver que $$S_{i} = a_i
b_i^\prime + a_i^\prime b_i = a_i  \mbox{ XOR }  b_i $$ et $$R_{i} = a_i b_i $$.

![img]({{site.baseurl}}/img/demi_add2.svg "Circuit demi-additionneur (en S de P)")
*Circuit demi-additionneur (en S de P)*

![img]({{site.baseurl}}/img/demi_add.svg "Circuit demi-additionneur avec porte XOR")
*Circuit demi-additionneur avec porte XOR*

### Additionneur complet

Une addition binaire complète de deux arguments constitués de $$n$$
bits procède du bit le moins significatif vers le bits le plus
significatif, en additionnant à chaque étape trois bits: $$a_{i}$$,
$$b_{i}$$ et $$r_{i-1}$$ et en produisant une somme $$S_{i}$$ et une
retenue $$R_{i}$$.

![img]({{site.baseurl}}/img/kmapSi_fulladder.svg "Diag-K pour $$S_i$$")
*Diag-K pour $$S_i$$*

![img]({{site.baseurl}}/img/kmap3fulladderR.svg "Diag-K pour $$R_i$$")
*Diag-K pour $$R_i$$*

Les expressions simplifiées sont 

$$ S_{i} = a_i^\prime b_i^\prime r_{i-1} + a_i^\prime b_i
r_{i-1}^\prime + a_i b_i^\prime r_{i-1}^\prime + a_i b_i r_{i-1} $$

$$ R_{i} = a_i b_i + a_i r_{i-1} + b_i r_{i-1} $$

![img]({{site.baseurl}}/img/fulladderS.svg "Circuit additionneur complet $$S_i$$")
*Circuit additionneur complet $$S_i$$*

![img]({{site.baseurl}}/img/fulladderR.svg "Circuit additionneur complet $$R_i$$")
*Circuit additionneur complet $$R_i$$*

Comme on le disait précédemment, il est possible de combiner deux
demi-additionneurs pour réaliser un additionneur complet, comme on peut le voir ici.

![img]({{site.baseurl}}/img/fulladderxor.svg "Circuit additionneur complet avec deux demi-additionneurs et une porte OU")
*Circuit additionneur complet avec deux demi-additionneurs et une porte OU*

