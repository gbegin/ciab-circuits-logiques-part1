---
title: Compteurs
---

## Compteurs

Un registre dont la séquence d'états est systématique est appelé un
**compteur**. Le comptage peut être contrôlé par une entrée spécifique
ou par l'entrée d'horloge. La séquence d'états est toujours la même
pour un type de compteur donné. Par exemple, les états d'un compteur
binaire à deux bits suivent la séquence $$00 \rightarrow 01
\rightarrow 10 \rightarrow 11 \rightarrow 00 \ldots $$ La sortie
correspond directement aux bits d'état. On distingue les compteurs
asynchrones et les compteurs synchrones. Quel que soit le type de
compteur, il y a toujours un retour vers l'état initial, car la
séquence d'états est un cycle.


### Compteur asynchrone

Dans un compteur binaire asynchrone, la sortie d'une bascule de poids
moins significatif est acheminée à l'entrée d'horloge de la bascule
suivante. C'est la transition de la sortie de la bascule de poids
moins significatif qui déclenche la bascule suivante. La figure
[712](#org93674d1) montre un compteur asynchrone construit à partir de
bascules T. La séquence de sortie est donnée dans le tableau
[61](#org783153e). On peut voir qu'après huit étapes, la séquence se
répète.

<table id="org783153e" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 52 :</span> Séquence du compteur</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$A_2$$</th>
<th scope="col" class="org-right">$$A_1$$</th>
<th scope="col" class="org-right">$$A_0$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>
</tbody>
</table>

Les compteurs asynchrones sont très simples, mais l'inconvénient est
que les transitions d'états ne sont pas synchrones. En particulier,
les bits d'état ne changent pas tous en même temps. Par exemple, si le
compteur passe de 0111 à 1000, la sortie peut passer par des états
intermédiaires parasites: 0111 $$\rightarrow$$ 0110 $$\rightarrow$$ 1100
$$\rightarrow$$ 1000.

![img]({{site.baseurl}}/img/rippleT3.svg "Compteur asynchrone")
*Compteur asynchrone*
