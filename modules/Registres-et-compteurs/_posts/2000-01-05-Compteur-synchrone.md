---
title: Compteur synchrone 
---

## Compteur synchrone

Dans un compteur synchrone, toutes les bascules sont commandées par un
même signal d'horloge, et les changements d'états sont
synchronisés. Les changements d'états sont contrôlés par les signaux
d'entrée appliqués aux bascules, comme dans le fonctionnement normal
d'un circuit séquentiel synchrone.

Le diagramme d'état d'un compteur trois bits (huit états) est un
cycle, comme on peut le voir sur la figure [715](#org70b5feb). Le tableau
d'états correspondant est donné dans le tableau [62](#orgbb470fd).

![img]({{site.baseurl}}/img/compt8_FSM.svg "Diagramme d'état d'un compteur")
*Diagramme d'état d'un compteur*

<table id="orgbb470fd" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 53 :</span> Tableau d'état du compteur</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$Z_2^n$$</th>
<th scope="col" class="org-right">$$Z_1^n$$</th>
<th scope="col" class="org-right">$$Z_0^n$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">$$Z_2^{n+1}$$</th>
<th scope="col" class="org-right">$$Z_1^{n+1}$$</th>
<th scope="col" class="org-right">$$Z_0^{n+1}$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>
</tbody>
</table>

Les expressions sont: 

$$  Z_2^{n+1} = Z_0^n \cdot Z_1^n \cdot (Z_2^{n})^\prime + (Z_0^{n})^\prime \cdot Z_2^n + (Z_1^{n})^\prime \cdot Z_2^n $$

$$  Z_1^{n+1} = Z_0^{n} \cdot (Z_1^{n})^\prime + (Z_0^{n})^\prime \cdot Z_1^n $$

$$  Z_0^{n+1} = (Z_0^{n})^\prime $$

Le schéma est donné à la figure [721](#org1539a4b).

![img]({{site.baseurl}}/img/compt8.svg "Schéma logique du compteur à 3 bits")
*Schéma logique du compteur à 3 bits*

On peut ajouter aux compteurs des fonctions diverses: comptage vers le
haut, comptage vers le bas, préchargement parallèle, remise à zéro,
etc.

Le compteur de la figure [721](#org1539a4b) a été conçu comme un circuit
séquentiel général, avec un décodeur de prochain état en forme *somme
de produits*. Il est également possible de concevoir un compteur
synchrone directement, sans passer par la méthodologie classique, en
suivant un raisonnement tout simple. La bascule du bit le moins
significatif $$Z_0$$ doit changer d'état à tous les coups
d'horloge. La bascule du bit suivant $$Z_1$$ doit changer d'état
seulement lorsque le bit précédent $$Z_0$$ vaut 1. La bascule du bit
suivant $$Z_2$$ doit changer d'état seulement lorsque les bits
précédents $$Z_1, Z_0$$ valent tous deux 1. Et on peut pousser le
raisonnement pour un compteur quelconque: 

> la bascule d'un bit $$Z_i$$
> doit changer d'état seulement lorsque les bits précédents
> $$Z_{i-1},Z_{i-2},\ldots, Z_0$$ valent tous 1.

Le compteur à quatre bits de la figure [726](#org9b7d006) a été conçu
selon cette approche, à partir de bascules JK.  L'utilisation d'une
porte AND par bascule permet de mettre en oeuvre les
conditions. L'entrée $$E$$ est un contrôle *enable* pour activer le
comptage. On a aussi prévu une sortie *Prochain* pour pouvoir
connecter en cascade d'autres compteurs.

![img]({{site.baseurl}}/img/compt_4bits.svg "Schéma logique du compteur à 4 bits")
*Schéma logique du compteur à 4 bits*

Si on réfléchit de la même façon au comptage vers le bas, on constate
que la règle devient:

> la bascule d'un bit $$Z_i$$ doit changer d'état
> seulement lorsque les bits précédents $$Z_{i-1},Z_{i-2},\ldots, Z_0$$
> valent tous 0.

Cette fois-ci, les conditions se baseront sur les sorties
complémentées des bascules précédentes.


### Compteur bidirectionnel

En combinant les deux conditions au moyen d'un multiplexeur deux-vers-
un, il est facile de concevoir un compteur haut/bas, tel qu'illustré
sur la figure [731](#orgba405e0).

![img]({{site.baseurl}}/img/compt_updown.svg "Schéma logique du compteur haut/bas à 4 bits")
*Schéma logique du compteur haut/bas à 4 bits*

