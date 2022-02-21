---
title: Autres compteurs
---
### Compteur en anneau

Un compteur en anneau est un registre à décalage connecté en boucle où
une seule bascule est active à la fois. Il y a donc dans la sortie un
seul bit 1, qui se décale  de façon cyclique: $$ 0010 \rightarrow 0001
\rightarrow 1000 \rightarrow 0100 \rightarrow 0010, \ldots$$ La
figure suivante illustre un compteur en anneau de quatre bits. Une
entrée *Init* permet d'injecter un bit 1 dans le registre au début. La
trace montre les formes d'onde obtenues.

On utilise fréquemment ce type de compteur pour générer des signaux de
synchronisation. En effet, chaque sortie devient active à son tour
dans le cycle, pendant une période d'horloge.

![img]({{site.baseurl}}/img/ring4.svg "Compteur en anneau à 4 bits")
*Compteur en anneau à 4 bits*

### Compteur Johnson

Un compteur Johnson permet de doubler le nombre d'états distincts par
rapport au compteur en anneau en injectant le complément du dernier
bit dans l'entrée du registre à décalage.  La figure suivante 
illustre un compteur en anneau Johnson de quatre bits, de même que la
trace de fonctionnement. La séquence d'états est données dans le
tableau [63](#org585130d).

![img]({{site.baseurl}}/img/johnson4.svg "Compteur Johnson à 4 bits")
*Compteur Johnson à 4 bits*

<table id="org585130d" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 54 :</span> Séquence d'états du compteur Johnson</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">No.</th>
<th scope="col" class="org-right">$$a$$</th>
<th scope="col" class="org-right">$$b$$</th>
<th scope="col" class="org-right">$$c$$</th>
<th scope="col" class="org-right">$$d$$</th>
<th scope="col" class="org-left">AND requis</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">$$a^\prime d^\prime $$</td>
</tr>


<tr>
<td class="org-right">2</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">$$a b^\prime $$</td>
</tr>


<tr>
<td class="org-right">3</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">$$b c^\prime $$</td>
</tr>


<tr>
<td class="org-right">4</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">$$c^\prime d^\prime $$</td>
</tr>


<tr>
<td class="org-right">5</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">$$a d^\prime $$</td>
</tr>


<tr>
<td class="org-right">6</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">$$a^\prime b $$</td>
</tr>


<tr>
<td class="org-right">7</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">$$b^\prime c $$</td>
</tr>


<tr>
<td class="org-right">8</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">$$c^\prime d $$</td>
</tr>
</tbody>
</table>

On peut construire des signaux de synchronisation distincts en
combinant deux par deux au moyen d'une porte AND des signaux de sortie
voisins (dans le cycle) ou leurs compléments. Le tableau [63](#org585130d)
donne les paires de sorties à combiner pour ce faire avec le compteur
Johnson de quatre bits.

Nous avons appliqué ce principe à un compteur Johsonson de deux bits,
présenté sur la figure ci-bas. La figure montre une trace
d'exécution avec les signaux de sortie. On y voit que chacun des
quatres signaux est activé à son tour.

![img]({{site.baseurl}}/img/johnson2_quad_decode.svg "Compteur Johnson à 2 bits")
*Compteur Johnson à 2 bits*

Si on s'intéresse aux sorties des bascules de ce même compteur Johnson, on peut voir sur la trace d'exécution de la figure suivante qu'on obtient des signaux en **quadrature**, c'est-à-dire que les sorties sont déphasées de 90 degrés les unes par rapport aux autres, comme le sont des fonctions $$ \sin(), \cos(), -\sin(), -\cos() $$.

![img]({{site.baseurl}}/img/johnson2_quad.svg "Compteur Johnson à 2 bits")
*Compteur Johnson à 2 bits*


### Diviseur de fréquence

Un compteur peut être utilisé pour diviser la fréquence d'un signal
périodique. Par exemple, la sortie d'un compteur à un bit change
d'état à tous les deux coups d'horloge, ce qui constitue une division
par deux de la fréquence d'horloge. Cette approche permet
naturellement des divisions par des puissances de deux.

On peut aussi utiliser un compteur Johnson, qui permettra alors, selon
le nombre d'étages du compteur, des divisions de fréquence par des
diviseurs, comme trois ou cinq, qui ne sont pas des puissances de deux.


### Compteur à chargement parallèle

Un compteur à chargement parallèle est illustré sur la figure
suivante. En activant l'entrée *Compte*, le comptage se fait vers le haut. En activant l'entrée *Charge*, les entrées $$ I_i, i=0, \ldots, 3$$ sont insérées dans les bascules. Il y a aussi une sortie *ov* qui indique lorsque le compteur atteint sa valeur maximale. Cette sortie peut être utilisée pour activer un autre compteur pour des bits de plus haut niveau.

![img]({{site.baseurl}}/img/compt_chargement.svg "Compteur à chargement parallèle")
*Compteur à chargement parallèle*

La trace d’exécution de la figure suivante montre le comptage de 4 jusqu'à 15 et retour à 0. On voit le signal *ov* s'activer sur 15.

![img]({{site.baseurl}}/img/compt_chargement_tracecompte.svg "Trace d'exécution, de 0 à 15")
*Trace d'exécution, de 0 à 15*

La trace de la figure suivante montre le compteur qui passe de 0 à 5, puis un chargement parallèle de la valeur 12.

![img]({{site.baseurl}}/img/compt_chargement_trace_charge.svg "Trace d'exécution, de 0 à 5 et chargement de 12")
*Trace d'exécution, de 0 à 5 et chargement de 12*


### Compteur modulo

On peut réaliser aisément un compteur modulo dont le cycle est plus
court que le maximum possible, en utilisant un compteur avec
chargement parallèle.  Par exemple, pour réaliser un compteur qui
compte de 0 jusqu'à 12, il suffit de décoder au moyen d'une porte AND
l'état qui doit être le dernier du cycle, et d'utiliser le signal de
sortie obtenu pour charger la valeur 0 dans le compteur. On obtient
ainsi un compteur modulo-13, dont le cycle compte 13 états.  La figure
illustre le compteur modulo-13, de même qu'une trace d'exécution sur
laquelle on voit le passage de 12 à 0.

![img]({{site.baseurl}}/img/compt_mod13.svg "Compteur modulo-13")
*Compteur modulo-13*

On pourrait aussi réaliser un compteur qui compte par exemple de 4 à
15, en utilisant cette fois la sortie *ov* pour activer le chargement
d'une valeur initiale 4.


