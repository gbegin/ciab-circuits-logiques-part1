---
title: Méthode Quine-McCluskey
---

## Tableau de couverture réduit

Le tableau de couverture réduit permet de se concentrer sur la
sélection des i.p. dont la sélection n'est pas évidente *a
priori*. Considérons pour illustrer la discussion le tableau de
couverture réduit suivant. $$m_c$$ est sans doute couvert pas un
i.p.e. qui n'est pas montré ici.

<table id="org08ebcc0" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 1 :</span> Tableau réduit</caption>

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
<td class="org-left">X</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">X</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
</tr>


<tr>
<td class="org-left">$$P_B$$</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">X</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">X</td>
</tr>


<tr>
<td class="org-left">$$P_C$$</td>
<td class="org-left">X</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">X</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
</tr>


<tr>
<td class="org-left">$$P_D$$</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">X</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">X</td>
</tr>


<tr>
<td class="org-left">$$P_E$$</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
<td class="org-left">X</td>
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

En cas d'égalité, comme on a ici pour $$m_e = m_g$$, on peut choisir quelle
colonne éliminer.

