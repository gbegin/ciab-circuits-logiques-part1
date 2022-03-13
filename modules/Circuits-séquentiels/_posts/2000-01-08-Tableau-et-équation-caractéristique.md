---
title: Tableau et équation caractéristique
---

### Tableaux caractéristiques

On résume le fonctionnement des différentes bascules au moyen de tableaux qui décrivent, selon les conditions d'entrée et l'état présent, quel sera le prochain état après le déclenchement. $$Q(t)$$ représente l'état présent et  $$Q(t+1)$$ l'état suivant.



<table id="orgd45c9c7" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 5 :</span> Bascule D</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$D$$</th>
<th scope="col" class="org-right">$$Q(t+1)$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-left">&#xa0;</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left"><i>reset</i></td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left"><i>set</i></td>
</tr>
</tbody>
</table>

<table id="org0899270" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 6 :</span> Bascule JK</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$J$$</th>
<th scope="col" class="org-right">$$K$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-left">$$Q(t+1)$$</th>
<th scope="col" class="org-left">&#xa0;</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">$$Q(t)$$</td>
<td class="org-left">pas de changement</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">0</td>
<td class="org-left"><i>reset</i></td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">1</td>
<td class="org-left"><i>set</i></td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">$$Q^\prime(t)$$</td>
<td class="org-left">basculement</td>
</tr>
</tbody>
</table>

<table id="org29d5fb7" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 7 :</span> Bascule T</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$T$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-left">$$Q(t+1)$$</th>
<th scope="col" class="org-left">&#xa0;</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">$$Q(t)$$</td>
<td class="org-left">pas de changement</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">$$Q^\prime(t)$$</td>
<td class="org-left">basculement</td>
</tr>
</tbody>
</table>




### Équations caractéristiques

On peut de même formuler des équations qui décrivent le comportement des bascules. Pour une bascule D, on a

$$ Q(t+1) = D $$.

Pour une bascule JK, on a

$$ Q(t+1) =J Q^\prime + K^\prime Q $$.

Pour une bascule T, on a

$$ Q(t+1) = T \mbox{ XOR } Q = T Q^\prime + T^\prime Q $$.


### Entrées asynchrones

Certaines bascules sont aussi munies d'entrées asynchrones, dont
l'effet n'est pas soumis à l'horloge. Ces entrées sont typiquement
utilisées pour faire un *reset* ou un *set* de la bascule, par exemple
pour une remise à zéro initiale d'un circuit séquentiel. Une
configuration typique est illustrée par la bascule de la figure
suivante qui comporte une entrée *Reset'* qui permet de
forcer l'état en agissant sur une porte NAND de chacune des paires de
portes. Cette entrée est active au niveau bas, c'est pourquoi il y a une indication de complément dans son symbole.

![img]({{site.baseurl}}/img/D_front_montant_setasyn.svg "Bascule D avec reset asynchrone")
*Bascule D avec reset asynchrone*
