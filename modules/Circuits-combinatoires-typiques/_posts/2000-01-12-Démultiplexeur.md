---
title: Démultiplexeur, encodeurs divers, portes 3 états
---

## Démultiplexeur

Un démultiplexeur achemine la valeur logique de son entrée à une sortie (parmi
$$2^n$$ sorties) sélectionnée par un code binaire de sélection. Le
démultiplexeur de la figure suivante comporte trois bits de sélection,
et permet donc d'acheminer la valeur de l'entrée $$I$$ vers une des
huit sorties $$O_i, i = 0, \ldots, 7$$. On peut aussi interpréter ce
circuit comme un décodeur trois-vers-huit avec une entrée signal de
contrôle (*enable*) $$I$$.

![img]({{site.baseurl}}/img/demux8.svg "Démultiplexeur un-vers-huit")
*Démultiplexeur un-vers-huit*

## Encodeurs divers

Il est possible de concevoir des encodeurs pour des fonctions
spécialisées, comme des encodeurs pour commander des affichages. La
démarche de conception s'apparente largement à celles que nous avons
vu dans les exemples précédents.


<a id="orgc0927dd"></a>

## Portes à trois états et tampon de bus

Les portes à trois états ajoutent un troisième état de fonctionnement
aux sorties: en plus des niveaux logiques bas et haut conventionnels,
un troisième état appelé **haute-impédance** fait en sorte que la sortie
se comporte comme si elle n'était plus connectée au circuit. La sortie
n'agit pas sur le reste du circuit, les autres portes dont les entrées
sont alimentés par la porte en haute-impédance ne sont aucunement
affectées par celle-ci. Pour activer cet état de sortie
haute-impédance, une entrée de contrôle est ajoutée.

Le figure ci-dessous montre une porte tampon à trois états. Avec
*Contrôle* = 0, la sortie est en haute impédance; avec *Contrôle* = 1,
la sortie est égale à l'entrée. 

![img]({{site.baseurl}}/img/buf_3s.svg "Porte tampon à trois états")
*Porte tampon à trois états*

En plaçant des tampons à trois états à chaque sortie d'un décodeur, on
peut réaliser un multiplexeur $$n$$-vers-un en reliant les sorties des
tampons à une sortie unique. Ainsi, lorsque qu'une entrée est
sélectionnée au moyen des entrées de sélection, c'est sa valeur qui se
retrouve à la sortie du dispositif. La valeur Z représente l'état
haute-impédance.  Lorsque l'entrée de contrôle $$E = 0$$, la sortie est
en haute-impédance.

<table id="org7c00c7f" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 32 :</span> Tableau de vérité pour un  multiplexeur quatre-vers-un trois états</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$s_1$$</th>
<th scope="col" class="org-right">$$s_0$$</th>
<th scope="col" class="org-right">$$E$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-left">$$I_0$$</th>
<th scope="col" class="org-left">$$I_1$$</th>
<th scope="col" class="org-left">$$ I_2$$</th>
<th scope="col" class="org-left">$$ I_3$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-left">$$Y$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">X</td>
<td class="org-right">X</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">Z</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">$$I_0$$</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">$$I_0$$</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">X</td>
<td class="org-left">$$I_1$$</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">$$I_1$$</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
<td class="org-left">$$I_2$$</td>
<td class="org-left">X</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">$$I_2$$</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
<td class="org-left">$$I_3$$</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">$$I_3$$</td>
</tr>
</tbody>
</table>

![img]({{site.baseurl}}/img/mux_4_1_3s.svg "Multiplexeur quatre-vers-un trois états")
*Multiplexeur quatre-vers-un trois états*

La fonctionnalité trois-états permet aussi de concevoir un
émetteur-récepteur de bus. Ce dispositif, illustré à la figure
suivante, permet d'établir une connexion bidirectionnelle entre I/O et
O/I. Lorsque l'entrée de contrôle $$E = 0 $$, c'est le tampon du haut
qui est actif, et O/I détermine la valeur de O/I. Lorsque $$E = 1 $$,
c'est le tampon du bas qui est actif, et I/O détermine la valeur de
O/I.

![img]({{site.baseurl}}/img/bus_trans.svg "Emetteur-récepteur de bus")
*Emetteur-récepteur de bus*


