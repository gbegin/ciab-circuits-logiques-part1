---
title: Diagramme d'état
---

# Diagramme d'état

Un diagramme d'état préliminaire est un bon point de départ pour
définir et étudier le comportement du système. On identifiera les
différents états par des lettres pour les distinguer sans faire
référence à des variables binaires de mémoire. Il s'agit dans un
premier temps d'un diagramme préliminaire, parce que le diagramme
final qui sera implémenté sera potentiellement différent.

À partir du diagramme d'état, il est possible de vérifier quelle
séquence de sortie correspond à une séquence d'entrée donnée.


## Tableau d'états

Un tableau d'états comporte une ligne par état présent et combinaison
d'entrées. Selon les combinaisons d'entrées possibles, on donne le
prochain état et les valeurs de sortie.


## Réduction du nombre d'états

Deux états sont équivalents si, pour chaque combinaison d'entrées, ils
produisent la même sortie et amènent le système dans le même état ou
dans un état équivalent. Considérons le diagramme d'état de la figure
suivante et le tableau d'état correspondant
[52](#org135cabe).

![img]({{site.baseurl}}/img/exemp_simplif_net.svg "Diagramme d'état")
*Diagramme d'état*

<table id="org1a30b39" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 1 :</span> Tableau d'état</caption>

<colgroup>
<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">État présent</th>
<th scope="col" class="org-right">x</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-left">État suivant</th>
<th scope="col" class="org-right">S</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">a</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">b</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">a</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">f</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">b</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">d</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">b</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">c</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">c</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">d</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">c</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">e</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">d</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">b</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">d</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">c</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">e</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">e</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">e</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">a</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">f</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">d</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">f</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">e</td>
<td class="org-right">0</td>
</tr>
</tbody>
</table>

En inspectant les différents états, on voit que les états *c* et *f* sont
équivalents. En remplaçant l'état *f* par l'état *c*, on obtient le
nouveau tableau d'état [52](#org135cabe).

<table id="org135cabe" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 2 :</span> Tableau d'état après une simplification</caption>

<colgroup>
<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">État présent</th>
<th scope="col" class="org-right">x</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-left">État suivant</th>
<th scope="col" class="org-right">S</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">a</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">b</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">a</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">c</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">b</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">d</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">b</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">c</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">c</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">d</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">c</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">e</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">d</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">b</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">d</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">c</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">e</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">e</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">e</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">a</td>
<td class="org-right">1</td>
</tr>
</tbody>
</table>

On voit maintenant que les états *a* et *d* sont équivalents. En
remplaçant l'état *d* par l'état *a*, on obtient le diagramme d'état
simplifié [53](#org71ff726). Il n'y a plus de simplification
possible. Nous sommes passés de six états à quatre.

<table id="org71ff726" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 3 :</span> Tableau d'état après simplification</caption>

<colgroup>
<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">État présent</th>
<th scope="col" class="org-right">x</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-left">État suivant</th>
<th scope="col" class="org-right">S</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">a</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">b</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">a</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">c</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">b</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">d</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">b</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">c</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">c</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">d</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">c</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">e</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">e</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">e</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">e</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">a</td>
<td class="org-right">1</td>
</tr>
</tbody>
</table>

Il faut bien s'assurer que le tableau d'état simplifié produit les
séquences de sortie désirées selon les séquences d'entrée appliquées.

