---
title: Autres types de bascules
---

## Autres types de bascules

Les fonctions du décodeur de prochain état se formulent naturellement
en fonction de bascules D.  Pour faire l'implémentation avec des
bascules JK ou T, il faut pouvoir déterminer les entrées nécessaires
pour amener les changements d'états requis. Pour ce faire, on
utilisera des **tableaux d'excitation** qui listent les combinaisons
d'entrées pour passer d'un état présent $$Q_n$$ à un état prochain
$$Q_{n+1}$$. Le tableau d'excitation pour une bascule JK est donné
dans le tableau [57](#org3bd819d) et celui pour une bascule T est donné
dans le tableau [58](#org5afbe8e).

<table id="org3bd819d" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 48 :</span> Tableau d'excitation, bascule JK</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$Q_n$$</th>
<th scope="col" class="org-right">$$Q_{n+1}$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-left">$$J$$</th>
<th scope="col" class="org-left">$$K$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">0</td>
<td class="org-left">X</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">1</td>
<td class="org-left">X</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">X</td>
<td class="org-left">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">X</td>
<td class="org-left">0</td>
</tr>
</tbody>
</table>

<table id="org5afbe8e" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 49 :</span> Tableau d'excitation, bascule T</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$Q_n$$</th>
<th scope="col" class="org-right">$$Q_{n+1}$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">$$T$$</th>
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

Reprenons le tableau de transition d'états pour notre exemple,
[56](#org3ed7c99), en ajoutant les signaux à générer pour des
bascules JK. On obtient alors le tableau [59](#orgec0f763).

<table id="orgec0f763" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 50 :</span> Tableau de transition d'états, avec bascules JK</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$ Z_1^n$$</th>
<th scope="col" class="org-right">$$ Z_0^n$$</th>
<th scope="col" class="org-right">$$ A$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">$$ Z_1^{n+1}$$</th>
<th scope="col" class="org-left">$$J$$</th>
<th scope="col" class="org-left">$$K$$</th>
<th scope="col" class="org-right">$$  Z_0^{n+1}$$</th>
<th scope="col" class="org-left">$$J$$</th>
<th scope="col" class="org-left">$$K$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-left">0</td>
<td class="org-left">X</td>
<td class="org-right">0</td>
<td class="org-left">0</td>
<td class="org-left">X</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-left">0</td>
<td class="org-left">X</td>
<td class="org-right">1</td>
<td class="org-left">1</td>
<td class="org-left">X</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-left">1</td>
<td class="org-left">X</td>
<td class="org-right">0</td>
<td class="org-left">X</td>
<td class="org-left">1</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-left">0</td>
<td class="org-left">X</td>
<td class="org-right">1</td>
<td class="org-left">X</td>
<td class="org-left">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-left">X</td>
<td class="org-left">1</td>
<td class="org-right">0</td>
<td class="org-left">0</td>
<td class="org-left">X</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-left">X</td>
<td class="org-left">0</td>
<td class="org-right">1</td>
<td class="org-left">1</td>
<td class="org-left">X</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-left">X</td>
<td class="org-left">0</td>
<td class="org-right">1</td>
<td class="org-left">x</td>
<td class="org-left">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-left">X</td>
<td class="org-left">0</td>
<td class="org-right">1</td>
<td class="org-left">x</td>
<td class="org-left">0</td>
</tr>
</tbody>
</table>

On trouve les expressions simplifiées suivantes:

$$ J_{Z_1} = A^\prime \cdot Z_0^n $$

$$ K_{Z_1} = A^\prime \cdot (Z_0^n)^\prime $$

$$ J_{Z_0} = A $$ 

$$ K_{Z_0} = (A + Z_1^n)^\prime $$

Ce qui nous donne l'implémentation de la figure suivante.

![img]({{site.baseurl}}/img/exemp_seq101_JK.svg "Détecteur pour la séquence 101, bascules JK")
*Détecteur pour la séquence 101, bascules JK*
