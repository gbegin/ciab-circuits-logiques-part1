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
dans le tableau [8](#org3bd819d) et celui pour une bascule T est donné
dans le tableau [9](#org5afbe8e).

<table id="org3bd819d" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 8 :</span> Tableau d'excitation, bascule JK</caption>

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
<caption class="t-above"><span class="table-number">Tableau 9 :</span> Tableau d'excitation, bascule T</caption>

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
bascules JK. On obtient alors le tableau [10](#orgec0f763).

<table id="orgec0f763" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 10 :</span> Tableau de transition d'états, avec bascules JK</caption>

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

## États interdits

Lorsque le nombre d'états nécessaires pour le fonctionnement de la
machine à état fini est strictement inférieur au nombre total d'états
possibles avec les bascules utilisées, un certain nombre d'états
(physiques) ne seront pas utilisés dans le fonctionnement normal du
circuit séquentiel. On parlera alors d'**états interdits**.  Lors de
la formulation des tableaux de vérité pour le décodeur de prochain
état, ces états donneront lieu à des cas facultatifs, qui pourront
permettre la simplification du circuit combinatoire du décodeur.

Il faut toutefois méfier de scénarios dans lesquels la machine à état
pourrait se retrouver dans un tel état interdit en raison d'un
dysfonctionnement momentané ou lors de la mise en marche du
système. Considérons par exemple un circuit séquentiel dont le
diagramme d'état (tel qu'implémenté après conception) est illustré
ci-dessous. En fonctionnement normal, le
système évolue entre les états *a*, *b* et *c*. Mais si pour une
raison quelconque, le système entre dans l'état *d*, il restera coincé
en bouclant sur cet état pour toujours (ou peut-être jusqu'à un
prochain dysfonctionnement).

![img]({{site.baseurl}}/img/etat_interdit.svg "Diagramme d'état avec état interdit")
*Diagramme d'état avec état interdit*

Une solution serait de modifier le décodeur de prochain état pour
s'assurer que, de l'état interdit, on revient toujours vers un état
normal, comme on peut le voir sur la figure suivante, où de l'état
*d*, on reviendra toujours vers l'état *c*.

![img]({{site.baseurl}}/img/etat_interdit_revient.svg "Diagramme d'état qui assure le retour en fonctionnement normal")
*Diagramme d'état qui assure le retour en fonctionnement normal*

## Exemple avec états *one-hot*

Dans cet exemple, on explore l'assignation d'états *one-hot* dans
laquelle il n'y a qu'un seul bit 1 par code binaire.

Considérons le diagramme d'état suivant.

![img]({{site.baseurl}}/img/exemple_one-hot.svg "Diagramme d'état pour *one-hot*")
*Diagramme d'état pour one-hot*

Le tableau d'assignation d'état correspondant est

<table id="org2b3b120" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 11 :</span> Assignation <i>one-hot</i></caption>

<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">État</th>
<th scope="col" class="org-right"><i>One-hot</i></th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">a</td>
<td class="org-right">100</td>
</tr>


<tr>
<td class="org-left">b</td>
<td class="org-right">010</td>
</tr>


<tr>
<td class="org-left">c</td>
<td class="org-right">001</td>
</tr>
</tbody>
</table>

Chaque état aura sa propre bascule active, dont les sorties seront
dénotées $$A$$, $$B$$ et $$C$$. Le tableau de transition d'états qu'on
obtient comporte un grand nombre de cas facultatifs et d'états
inutilisés, que nous n'avons pas indiqués ici. Le tableau
[2](#org0db4b7d) ne montre que les six transitions spécifiées
dans le diagramme d'état.

<table id="org0db4b7d" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 12 :</span> Tableau de transition d'états <i>one-hot</i></caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$A^n$$</th>
<th scope="col" class="org-right">$$B^n$$</th>
<th scope="col" class="org-right">$$C^n$$</th>
<th scope="col" class="org-left">$$x$$</th>
<th scope="col" class="org-left">$$y$$</th>
<th scope="col" class="org-left">$$z$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">$$A^{n+1}$$</th>
<th scope="col" class="org-right">$$B^{n+1}$$</th>
<th scope="col" class="org-right">$$C^{n+1}$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">0</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">1</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">X</td>
<td class="org-left">0</td>
<td class="org-left">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">X</td>
<td class="org-left">0</td>
<td class="org-left">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">X</td>
<td class="org-left">1</td>
<td class="org-left">X</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
</tr>
</tbody>
</table>

Il est possible de formuler le décodeur de prochain état directement,
par inspection des transitions spécifiées.  Si on considère les
transitions qui entrent dans l'état *a*, il y a trois façons différentes
d'arriver en *a*:

-   à partir de *a*, sous la condition $$x=0$$
-   à partir de *b*, sous la condition $$y=0, z=1$$
-   à partir de *c*, sans conditions

L'équation de prochain état pour *a* sera ainsi 
$$
A^{n+1} = A^{n}x^\prime + B^n y^\prime z + C^n
$$

Le même raisonnement nous permet d'écrire pour les autres bascules:
$$
B^{n+1} = A^{n}x + B^n y^\prime z^\prime
$$
et 
$$
C^{n+1} = B^n y
$$

Le décodeur de prochain état est simplifié, car les bits d'état
offrent une indication directe de l' état dans lequel la machine se
trouve. Le fonctionnement de la machine entraîne peu de transitions,
ce qui résulte en une consommation d'énergie réduite, et moins de
risque de *glitches*. La vitesse de commutation ne dépend pas du
nombre d'états. Ajouter ou retrancher un état peu se faire sans avoir
à tout refaire la conception.  L'assignation *one-hot* est
particulièrement intéressante lorsqu'on est moins limité par le nombre
de bascules que par le nombre d'éléments combinatoires. 

Le principal inconvénient est la croissance du nombre de bascules, qui
est linéaire avec le nombre d'états plutôt que logarithmique. Par
exemple, pour 30 états, il faudra 30 bascules alors qu'avec un
encodage binaire, il n'en faudrait que cinq. Il faut aussi considérer
qu'il y a un grand nombre d'états interdits, et prendre les
précautions qui s'imposent pour éviter les problèmes de fonctionnement
coincé.

