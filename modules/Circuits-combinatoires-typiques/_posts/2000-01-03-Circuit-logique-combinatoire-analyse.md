---
title: Circuit-logique-combinatoire-analyse
---
## Analyse d'un circuit logique combinatoire

Si on est placé devant le schéma d'un circuit logique dont on ne connaît pas la fonction, on doit en faire l'analyse. La première étape consiste à vérifier qu'il s'agit bien d'un circuit combinatoire. Si le schéma ne comporte pas de cellules de mémoire ou de boucles de rétroaction, on peut conclure que le circuit est combinatoire. Une boucle de rétroaction consiste en un chemin dans le circuit dans lequel une valeur d'entrée d'une porte provient, directement ou indirectement (par l'intermédiaire d'autres portes), de la sortie de la même porte. La présence de rétroaction est une caractéristique des circuits logiques séquentiels, que nous étudierons plus loin.

Pour interpréter le comportement du circuit, nous devons déterminer les expressions logiques qu'il met en oeuvre ou établir son tableau de vérité.

Pour déterminer l'expression logique, on procède ainsi:

1.  Étiqueter toutes les sorties des portes qui sont alimentées par les variables d'entrée du système. Les noms de variables seront arbitraire, mais devrait être choisis de façon à faciliter l'interprétation par la suite. Déterminer les fonctions logiques pour ces variables.
2.  Étiqueter les sorties des portes qui sont alimentées par les variables d'entrée et par les sorties étiquetées à l'étape précédente. Déterminer les fonctions logiques pour ces nouvelles variables.
3.  Répéter l'étape 2 jusqu'à arriver aux variables de sortie du système.
4.  En substituant les expressions logiques des fonctions identifiées, déterminer l'expression logique pour les sorties du système en fonction des entrées du système.


### Exemple

Considérons le circuit combinatoire à analyser suivant:

![img]({{site.baseurl}}/img/circuit_logique_inconnu.svg "Circuit combinatoire à analyser")
*Circuit combinatoire à analyser*

1.  Il n'est pas la peine d'étiqueter la sortie de la porte
    inverseur. Comme variables intermédiaire, nous considérons $$I_1$$
    en sortie de la porte ET à trois entrées et $$I_2$$ en sortie de la
    porte NOR. On trouve que $$ I_1 = A^\prime \cdot B \cdot C $$ et que
    $$ I_2 = (A + D)^\prime = A^\prime \cdot D^\prime $$.

2.  On aura donc $$ F_1 = I_1 \cdot I_2 $$.

3.  En substituant, $$ F_1 = ( A^\prime \cdot B \cdot C ) \cdot (
       A^\prime \cdot D^\prime) = A^\prime \cdot B \cdot C \cdot D^\prime
       $$.

4.  En simplifiant, on obtient finalement $$F_1 = A^\prime \cdot B
       \cdot C \cdot D^\prime $$.

<table id="orgfdd76b5" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 1 :</span> Tableaux de vérité des fonctions intermédiaires et de la sortie</caption>

<colgroup>
<col  class="org-right" />

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
<th scope="col" class="org-right">$$A$$</th>
<th scope="col" class="org-right">$$C$$</th>
<th scope="col" class="org-right">$$B$$</th>
<th scope="col" class="org-right">$$D$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">$$I_1$$</th>
<th scope="col" class="org-right">$$I_2$$</th>
<th scope="col" class="org-right">$$F_1$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
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
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
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

