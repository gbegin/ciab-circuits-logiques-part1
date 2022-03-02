---
title: Analyse pour des bascules JK
---

## Analyse pour des bascules JK

Pour analyser un circuit séquentiel utilisant des bascules JK, on
détermine d'abord les expressions $$J_A$$ et $$K_A$$, $$J_B$$ et
$$K_B$$, etc., pour chacune des bascules. On doit ensuite se référer
au tableau caractéristique pour ce type de bascule [47](#org43c5ee1) pour
déterminer quelles seront les prochaines valeurs de sortie pour
chacune des bascules. L'exemple suivant illustre la procédure.

### Exemple avec bascules JK

![img]({{site.baseurl}}/img/seq_JK.svg "Exemple circuit séquentiel JK")
*Exemple circuit séquentiel JK*

À partir des expression des entrées $$J$$ et $$K$$ suivantes:

$$ J_0 = (q_1^{n})^\prime $$

$$ K_0 = q_0^{n} \cdot (q_1^{n})^\prime $$

$$ J_1 = q_0^{n} $$

$$ K_1 = (q_0^{n})^\prime \cdot q_1^{n} $$

on peut remplir le tableau d'excitation.

<table id="orgd626e95" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 41 :</span> Tableau d'excitation circuit séquentiel JK</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$q_1^{n+1}$$</th>
<th scope="col" class="org-right">$$q_0^n$$</th>
<th scope="col" class="org-right">$$J_0$$</th>
<th scope="col" class="org-right">$$K_0$$</th>
<th scope="col" class="org-right">$$J_1$$</th>
<th scope="col" class="org-right">$$K_1$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">$$q_1^{n+1}$$</th>
<th scope="col" class="org-right">$$q_0^{n+1}$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
</tr>
</tbody>
</table>

À partir du tableau d'excitation, on peut tracer le diagramme d'état.

![img]({{site.baseurl}}/img/seq_JKb_FSM.svg "Diagramme d'état circuit séquentiel JK")
*Diagramme d'état circuit séquentiel JK*

