---
title: Soustraction
---

### Soustraction

Pour effectuer une soustraction $$A - B$$, il faut effectuer $$A +
(-B)$$, c’est-à-dire additionner le complément à deux de $$B$$ à
$$A$$. On détermine le complément à deux en obtenant d'abord le
complément à un en complémentant chaque bit, et en additionnant ensuite
1 à cette valeur par le biais de l'entrée de retenue de l'additionneur. Il
est ainsi possible de concevoir un additionneur/soustracteur commandé
par un signal de contrôle $$O$$. Si $$O=0$$, le circuit calcule $$A +
(B)$$ et si $$O=1$$, le circuit calcule $$A + (-B)$$.

La complémentation de $$B$$ se fait au moyen de portes XOR qui
calculent $$O  \mbox{ XOR }  b_i$$ et dont la sortie est acheminée à l'entrée
$$B$$ de l'additionneur. Lorsque que $$O=1$$, leur sortie vaut
$$b_i^\prime$$.

![Circuit additionneur/soustracteur 4 bits.]({{site.baseurl}}/img/add_sous.svg "Circuit additionneur/soustracteur 4 bits")
*Circuit additionneur/soustracteur 4 bits*

### Débordements

Un additionneur ou un soustracteur sont conçus en fonction d'une
taille de nombres $$n$$. Lorsque le résultat de l'opération dépasse la
limite pouvant être représentée, on doit détecter cette condition et
la signaler par un signal binaire.

Le cas de l'addition de nombre non signés est le plus simple. Il
suffit de surveiller la retenue du niveau le plus significatif. Une
retenue de 1 signifie un débordement de l'addition.

Les calculs avec des nombres signés en complément à deux peuvent aussi
occasionner des débordements, mais la détection doit tenir compte des
bits qui indiquent le signe des nombres.

L'addition de deux nombres de signes différents ne peut pas
occasionner de débordement, puisque la valeur absolue du résultat sera
nécessairement moindre que celle du plus grand des nombres
initiaux. Un débordement ne peut donc se produire que si les deux
nombres additionnés sont de même signe, deux positifs ou deux
négatifs.

Prenons le cas de nombres représentés sur huit bits en complément à
deux. La gamme représentable va de -128 à +127 avec un bit qui
représente le signe. Si on additionne (+50)10 = (00110010)2 avec
(+100)10 = (01100100)2, aura un débordement, car $$150 > 127$$. On
voit dans le tableau suivant les bits qui seront produits par l'addition,
avec en évidence les retenues des deux derniers niveaux. Le bit de
signe a été séparé des autres.

<table id="orgf92473f" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 4 :</span> Addition de (+50)10 + (+100)10 = (00110010)2 + (01100100)2</caption>

<colgroup>
<col  class="org-left" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Retenues</th>
<th scope="col" class="org-right">0</th>
<th scope="col" class="org-right">1</th>
<th scope="col" class="org-left">&#xa0;</th>
</tr>


<tr>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">&#xa0;</th>
<th scope="col" class="org-right">0</th>
<th scope="col" class="org-left">011 0010</th>
</tr>


<tr>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">&#xa0;</th>
<th scope="col" class="org-right">0</th>
<th scope="col" class="org-left">110 0100</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">&#xa0;</td>
<td class="org-right">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-left">001 0110</td>
</tr>
</tbody>
</table>

Refaisons le même exercice avec deux nombres négatifs: on additionne
(-50)10 = (1100 1110)2 avec (-100)10 = (1001 1100)2, qui créera un
débordement aussi. 

<table id="orgeae1ca6" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 5 :</span> Addition de (-50)10 + (-100)10 = (1100 1110)2 + (1001 1100)2</caption>

<colgroup>
<col  class="org-left" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Retenues</th>
<th scope="col" class="org-right">1</th>
<th scope="col" class="org-right">0</th>
<th scope="col" class="org-left">&#xa0;</th>
</tr>


<tr>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">&#xa0;</th>
<th scope="col" class="org-right">1</th>
<th scope="col" class="org-left">100 1110</th>
</tr>


<tr>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">&#xa0;</th>
<th scope="col" class="org-right">1</th>
<th scope="col" class="org-left">001 1100</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">&#xa0;</td>
<td class="org-right">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-left">110 1010</td>
</tr>
</tbody>
</table>

On peut dans les deux cas détecter le débordement en observant que la
retenue du dernier niveau et la retenue de l'avant dernier niveau sont
différentes. On peut vérifier facilement que les autres cas sans
débordement donnent des retenues égales. Si on fait un OU-exclusif
entre ces deux retenues, un résultat 1 indiquera un débordement. Ce
mécanisme de détection de débordement a été ajouté au circuit
additionneur/soustracteur 4 bits dans la figure suivante pour générer
le signal $$D$$ qui indique un débordement.

![Circuit additionneur/soustracteur 4 bits avec débordement.]({{site.baseurl}}/img/add_sous_deb.svg "Circuit additionneur/soustracteur 4 bits avec débordement")
*"Circuit additionneur/soustracteur 4 bits avec débordement*

