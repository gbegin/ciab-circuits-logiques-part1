---
title: Méthode Quine-McCluskey
---
## Tableau de couverture Quine-McCluskey

La méthode de Quine-McCluskey systématise la sélection des impliquants
en se basant sur des relations qui s'expriment en fonction d'un
tableau de couverture.

Un **tableau de couverture** comporte une ligne pour chaque i.p. et
une colonne pour chaque minterm de la fonction à minimiser $$z$$. Un
&#10003; est inscrit à l'intersection de la ligne $$i$$ et de la
colonne $$j$$ si l'i.p.  $$P_i$$ de la ligne $$i$$ couvre le minterm
$$m_j$$ de la colonne $$j$$.

Le problème de minimisation devient alors: trouver une couverture pour
la fonction $$z$$ qui

1.  contient le nombre minimum de lignes

2.  est telle qu'aucune autre couverture à nombre de ligne minimum
    comprend moins d'entrées 1 et 0 dans ses codes d'impliquants de
    ligne.

Dans le tableau de couverture, on identifie facilement les i.p.e. par
les colonnes qui ne contiennent qu'un &#10003;. L'i.p. qui couvre une
colonne qui ne contient qu'un &#10003; est un i.p.e.

Puisque les i.p.e. doivent faire partie de la solution finale, toutes
les colonnes couvertes par des i.p.e. seront couvertes dans n'importe
quelle solution. On peut donc éliminer ces colonnes de la suite de la
recherche de la solution, de même que les lignes correspondant aux
i.p.e. On obtient ainsi un tableau de couverture **réduit**.

**Il ne faut cependant pas oublier de mettre les i.p.e. dans la solution
finale.**

## Tableau de couverture réduit

Le tableau de couverture réduit permet de se concentrer sur la
sélection des i.p. dont la sélection n'est pas évidente *a
priori*. Considérons pour illustrer la discussion le tableau de
couverture réduit suivant. $$m_c$$ est sans doute couvert pas un
i.p.e. qui n'est pas montré ici.

<table id="org08ebcc0" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 3 :</span> Tableau réduit</caption>

<colgroup>
<col  class="org-left" />

<col  class="org-left" />

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
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-left">$$m_a$$</th>
<th scope="col" class="org-left">$$m_b$$</th>
<th scope="col" class="org-left">$$m_c$$</th>
<th scope="col" class="org-left">$$m_d$$</th>
<th scope="col" class="org-left">$$m_e$$</th>
<th scope="col" class="org-left">$$m_f$$</th>
<th scope="col" class="org-left">$$m_g$$</th>
<th scope="col" class="org-left">$$m_h$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">$$P_A$$</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#10003;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#10003;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#10003;</td>
<td class="org-left">&#10003;</td>
</tr>


<tr>
<td class="org-left">$$P_B$$</td>
<td class="org-left">&#10003;</td>
<td class="org-left">&#10003;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#10003;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#10003;</td>
</tr>


<tr>
<td class="org-left">$$P_C$$</td>
<td class="org-left">&#10003;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#10003;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#10003;</td>
<td class="org-left">&#10003;</td>
</tr>


<tr>
<td class="org-left">$$P_D$$</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#10003;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#10003;</td>
</tr>


<tr>
<td class="org-left">$$P_E$$</td>
<td class="org-left">&#10003;</td>
<td class="org-left">&#10003;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#10003;</td>
<td class="org-left">&#10003;</td>
<td class="org-left">&#10003;</td>
<td class="org-left">&#10003;</td>
<td class="org-left">&#10003;</td>
</tr>
</tbody>
</table>


## Dominance de lignes

Une ligne $$P_i$$ domine une ligne $$P_j$$ (noté $$P_i \supseteq
P_j$$) si la ligne $$P_i$$ contient un x dans toutes les colonnes où
la ligne $$P_j$$ contient un x. Ici, on a $$P_B \supseteq P_D$$ mais
$$P_B$$ ne domine pas $$P_A$$. On peut voir aussi que $$P_E$$ domine
plusieurs lignes.

En général, une $$P_i$$ dominante contient plus de x que $$P_j$$. Si
elles ont le même nombre de x (dans les mêmes colonnes), on a $$P_i =
P_j$$. Il n'y a pas de cas d'égalité ici.

Une ligne **dominée** par une autre peut être éliminée du tableau de
couverture à condition que son nombre de littéraux soit supérieur ou
égal à celui de la ligne dominante.


## Dominance de colonnes

Une colonne $$m_i$$ domine une colonne $$m_j$$ (noté $$m_i \supseteq
m_j$$) si la colonne $$m_i$$ contient un x dans toutes les lignes où
la colonne $$m_j$$ contient un x. Ici, la colonne $$m_h \supseteq
m_g$$ mais $$m_b$$ ne domine pas $$m_a$$. 

Une colonne **dominant** une autre peut être éliminée du tableau de
couverture, car le fait que la solution finale couvre la colonne
dominée assure que la colonne dominante sera couverte aussi. Donc ici,
la colonne $$m_h$$ peut être éliminée.

En cas d'égalité, comme on a ici pour $$m_e = m_g$$, on peut librement
choisir quelle colonne éliminer.

