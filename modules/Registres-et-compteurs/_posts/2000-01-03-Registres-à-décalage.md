---
title: Registres à décalage
---

## Registres à décalage

Un registre à décalage consiste en une chaîne de bascules, la sortie
de l'une reliée à l'entrée de la suivante. La figure [704](#org01bbfba) montre
un registre à décalage de quatre bits. À chaque coup d'horloge,
l'entrée est insérée dans la première bascule, à droite, et le contenu
du registre est décalé d'une position vers la gauche. La sortie
provient de la dernière bascule à droite.

![img]({{site.baseurl}}/img/shift4.svg "Registre à décalage 4 bits")
*Registre à décalage 4 bits*

En utilisant un multiplexeur quatre-vers-un pour sélectionner ce qui
sera inséré dans une bascule, il est possible de concevoir un registre
à décalage universel. Les différents opérations sont le *maintien*, le
*décalage à droite* avec entrée $$G$$, le *décalage à gauche* avec entrée
$$D$$ et le *chargement parallèle*, avec les entrées $$I_i, i=1, \ldots,
4$$.

Les différentes opérations sont commandées par les deux signaux de
sélection, tel qu'indiqué dans le tableau [60](#orgbda54ca).

<table id="orgbda54ca" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 51 :</span> Codes de sélection et opérations</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">Sél.</th>
<th scope="col" class="org-left">Action</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">00</td>
<td class="org-left">Maintien</td>
</tr>


<tr>
<td class="org-right">01</td>
<td class="org-left">Décalage droite</td>
</tr>


<tr>
<td class="org-right">10</td>
<td class="org-left">Décalage gauche</td>
</tr>


<tr>
<td class="org-right">11</td>
<td class="org-left">Chargement parallèle</td>
</tr>
</tbody>
</table>

![img]({{site.baseurl}}/img/shift4_univ.svg "Registre à décalage universel") 
*Registre à décalage universel*

Les registres à décalage sont notamment utilisés pour convertir des
données parallèles en données sérielles et vice versa, des opérations
très utiles dans le contexte d'interfaces de communication. On peut
également s'en servir pour faire des multiplications ou divisions par
deux, comme on l'a vu à la section [Multiplication et division par deux]({{site.baseurl}}{% post_url modules/Systèmes-de-numération/2000-01-04-opérations %}).
