---
title: Algèbre de Boole
---
# Formalisme mathématique

Un formalisme mathématique, élaboré bien avant l'avènement des
circuits électroniques numériques, permet de formuler, analyser et
simplifier les expressions de la logique binaire. Il s'agit de
l'algèbre de Boole. 


## Définitions

Une algèbre est un système mathématique, défini pour un ensemble
d'éléments auxquels sont associés un ensemble d'opérateurs et qui
respecte un jeu d'axiomes ou postulats. Une algèbre nécessite donc:

1.   Un ensemble $$S$$ d'éléments

2.   Des opérateurs: $$\cdot$$, $$\star$$, $$+$$

3.   L'application des opérateurs aux différents éléments doit respecter
    un certain nombre de propriétés appelées postulat, comme par exemple:

        -  Fermeture
        -  Associativité
        -  Commutativité
        -  Existence d'élément identité
        -  Existence d'élément inverse
        -  Distributivité

Selon le choix des postulats, on arrive à définir différents types de
systèmes algébriques. Par exemple, les nombres réels avec lequel nous
sommes familiers est un système algébrique d'un type appelé **corps**.


## Algèbre de Boole

Une algèbre de Boole est un type de système algébrique défini sur un
ensemble $$B$$, muni de deux opérateurs dénotés $$+$$ et $$\cdot$$, et qui
respecte les postulats suivants<sup><a id="fnr.2" class="footref"
href="#fn.2" role="doc-backlink">2</a></sup> (postulats de
Huntington):

1.  Fermeture: tout résultat d'une opération sur un élément de
    l'ensemble donne un élément de l'ensemble.
    1.  &spades; Fermeture par rapport à $$+$$.
    
    2.  &hearts; Fermeture par rapport à $$\cdot$$.

2.  Éléments identité
    1.  &spades; Élément identité de $$+$$, noté 0. $$x + 0 = 0 + x = x$$.
    
    2.  &hearts; Élément identité de $$\cdot$$, noté 1. $$x \cdot 1 =
        1 \cdot x = x$$.

3.  Commutativité
    1.  &spades; Commutativité par rapport à $$+$$. $$x + y = y + x$$.
    
    2.  &hearts; Commutativité par rapport à $$\cdot$$. $$x \cdot y =
        y \cdot x$$.

4.  Distributivité
    1.  &spades; $$\cdot$$ est distributif sur $$+$$. $$x \cdot (y +
        z)= (x \cdot y) + (x \cdot z)$$.
    
    2.  &hearts; $$+$$ est distributif sur $$\cdot$$. $$x + (y \cdot
        z)= (x + y) \cdot (x + z)$$.

5.  Pour chaque élément $$x \in B$$, il existe un élément $$x^{\prime}
    \in B$$ (appelé complément de $$x$$) tel que
    1.  &spades; $$x + x^{\prime} = 1$$.
    
    2.  &hearts; $$x \cdot x^{\prime} = 0$$.

6.  Il existe au moins deux éléments $$x, y \in B$$ tels que $$x \neq y$$.

Observons des différences entre une algèbre de Boole et le corps des réels:

1.  Il n'y a pas de loi d'associativité dans les postulats. On peut en
    démontrer une, cependant.

2.  L'opération $$+$$ est distributive sur $$\cdot$$.

3.  Il n'y a pas d'inverse multiplicatif ni d'inverse additif, on ne
    peut donc pas faire de soustraction ou de division.

4.  Il y a un concept de complément.

5.  L'ensemble d'éléments est différent. Nous utiliserons pour notre
    part l'ensemble $$B: \{0, 1 \}$$ pour notre algèbre de Boole.


## Algèbre de Boole à deux valeurs

L'ensemble de définition: $$B : \{0, 1 \}$$.

Opérateur $$\cdot$$:

<div class="org-center">
<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$x$$</th>
<th scope="col" class="org-right">$$y$$</th>
<th scope="col" class="org-right">&#xa0;</th>
<th scope="col" class="org-right">$$x \cdot y$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">&#xa0;</td>
<td class="org-right">1</td>
</tr>
</tbody>
</table>
</div>

Opérateur $$+$$:

<div class="org-center">
<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$x$$</th>
<th scope="col" class="org-right">$$y$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">$$x + y$$</th>
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
<td class="org-right">1</td>
</tr>
</tbody>
</table>
</div>

Règle de complémentation:

<div class="org-center">
<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$x$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">$$x^{\prime}$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


</tbody>
</table>
</div>


## Vérification des postulats

1.  La fermeture est évidente (en regardant les tableaux des opérations).

2.  En observant les tableaux de vérité, on constate que
    
    1.  $$0 + 0 = 0$$, $$0 + 1 = 1 + 0 = 1$$
    
    2.  $$1 \cdot 1 = 1$$, $$0 \cdot 1 = 1 \cdot 0 = 0$$
    
    ce qui définit les deux éléments identité: 0 pour $$+$$ et 1 pour  $$\cdot$$.

3.  La commutativité des lois est évidente: les tableaux sont
    symétriques.

4.  Les lois de distributivité se démontrent aisément en établissant des
    tables de vérité pour les différentes valeurs de $$x, y$$ et $$z$$.

5.  Par le tableau de complément, on vérifie que
    1.  $$x + x^{\prime} = 1$$, car $$0 + 0^{\prime} = 0 + 1 = 1$$ et $$1 +
                1^{\prime} = 1+ 0 = 1$$
    
    2.  $$x \cdot x^{\prime} = 0$$ car $$0 \cdot 0^{\prime} = 0 \cdot 1 =
                0$$ et $$1 \cdot 1^{\prime} = 1 \cdot 0 = 0$$.

6.  Le postulat 6 est vérifié car il y a deux éléments distincts: 0 et 1.


<sup><a id="fn.2" class="footnum" href="#fnr.2">2</a></sup> Certains
postulats viennent en paires; nous les distinguons ici au moyen
d'étiquettes &spades; ou &hearts;.
