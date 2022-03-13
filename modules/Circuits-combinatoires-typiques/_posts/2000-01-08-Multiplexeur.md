---
title: Multiplexeur
---

## Multiplexeur

Un multiplexeur est un circuit combinatoire qui sélectionne le signal
qui provient d'une de ses entrées, et fait que sa sortie soit égale à
l'entrée sélectionnée. Les signaux de sélection fonctionnent
typiquement selon un encodage binaire, ce qui suppose un nombre
d'entrées de la forme $$2^n$$. On désigne le multiplexeur par le
nombre de signaux d'entrées à sélectionner.


### Multiplexeur deux-vers-un

Le multiplexeur le plus simple utilise un seul signal de sélection
$$S$$ qui permet de choisir une de deux entrées $$I_0$$ ou $$I_1$$
pour agir sur la sortie $$Y$$.

![img]({{site.baseurl}}/img/mux2b.svg "Circuit du multiplexeur deux-vers-un")
*Circuit du multiplexeur deux-vers-un*

![img]({{site.baseurl}}/img/mux2symb.svg "Symbole du multiplexeur deux-vers-un")
*Symbole du multiplexeur deux-vers-un*


### Multiplexeur quatre-vers-un

Un multiplexeur quatre-vers-un permet de choisir une de quatre entrées
en utilisant deux signaux de sélection. Pour simplifier la
représentation symbolique, les deux signaux de sélection sont
représentés comme un seul fil, qui correspond en fait à une paire de
signaux $$S_0$$ et $$S_1$$. Pour un multiplexeur à $$2^n$$ entrées, on
aurait un vecteur de $$n$$ signaux de sélection.

![img]({{site.baseurl}}/img/mux4.svg "Circuit du multiplexeur quatre-vers-un")
*Circuit du multiplexeur quatre-vers-un*

![img]({{site.baseurl}}/img/mux4symb.svg "Symbole du multiplexeur quatre-vers-un")
*Symbole du multiplexeur quatre-vers-un*


<table id="orgf6a5ff8" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 6 :</span> Tableau de vérité du multiplexeur quatre-vers-un</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$S_1$$</th>
<th scope="col" class="org-right">$$S_0$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-left">$$Y$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">$$I_0$$</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">$$I_1$$</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">$$I_2$$</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">$$I_3$$</td>
</tr>
</tbody>
</table>

