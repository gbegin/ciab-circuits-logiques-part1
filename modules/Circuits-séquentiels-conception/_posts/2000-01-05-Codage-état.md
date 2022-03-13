---
title: Codage des états
---

## Codage des états

Une fois que le nombre d'états a été réduit, il faut assigner des
codes binaires aux états. Si on doit coder $$m$$ états, il faudra
$$n$$ bits, avec $$ 2^n \geq m$$. Si le nombre de combinaisons
binaires est plus grand que le nombre d'état nécessaires, les
combinaisons inutilisées seront considérées comme des cas facultatifs.

Le choix d'une assignation des codes aux états aura des répercussions
sur la complexité du décodeur de prochain état, et sur le décodeur de
sortie. Plusieurs options peuvent être envisagées: assigner des codes
dans l'ordre naturel d'énumération binaire, assigner selon un code
Gray, ou encore choisir une assignation où il y a un seul bit 1 par
code binaire (approche dite *one-hot*). L'approche *one-hot* requiert
plus de bascules, mais permet souvent de simplifier les décodeurs de
prochain état et de sortie. Le tableau [5](#org4cfbb66) montre
un exemple possible d'assignation pour chacune de ces approches.

<table id="org4cfbb66" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 5 :</span> Possibilités d'assignation de codes d'états</caption>

<colgroup>
<col  class="org-left" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">État</th>
<th scope="col" class="org-right">Binaire</th>
<th scope="col" class="org-right">Gray</th>
<th scope="col" class="org-right"><i>One-hot</i></th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">a</td>
<td class="org-right">00</td>
<td class="org-right">00</td>
<td class="org-right">0001</td>
</tr>


<tr>
<td class="org-left">b</td>
<td class="org-right">01</td>
<td class="org-right">01</td>
<td class="org-right">0010</td>
</tr>


<tr>
<td class="org-left">c</td>
<td class="org-right">10</td>
<td class="org-right">11</td>
<td class="org-right">0100</td>
</tr>


<tr>
<td class="org-left">e</td>
<td class="org-right">11</td>
<td class="org-right">10</td>
<td class="org-right">1000</td>
</tr>
</tbody>
</table>

