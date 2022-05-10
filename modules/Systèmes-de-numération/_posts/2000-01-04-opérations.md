---
title: Opérations
---
## Nombres binaires fractionnaires

Il est aussi possible de représenter des nombres fractionnaires en
base deux. En gardant à l'esprit que la position d'un bit détermine sa
valeur, il suffit d'étendre le principe déjà établi aux bits qui
seront placés après la virgule qui sépare la partie entière de la
partie fractionnaire. Les indices des positions à droite de la virgule
seront négatifs.

Le tableau [7](#org473ef5b) donne par exemple le détail de l'évaluation
de la valeur du nombre fractionnaire (101,11)2. On obtient comme
valeur $$1 \times 4 + 0 \times 2 + 1 \times 1 + 1 \times 1/2 + 1
\times 1/4 = 5,75$$.

<table id="org473ef5b" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 7 :</span> évaluation de la valeur du nombre fractionnaire (101,11)2</caption>

<colgroup>
<col  class="org-left" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Position</th>
<th scope="col" class="org-right">2</th>
<th scope="col" class="org-right">1</th>
<th scope="col" class="org-right">0</th>
<th scope="col" class="org-right">-1</th>
<th scope="col" class="org-right">-2</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">Valeur</td>
<td class="org-right">$$2^2$$</td>
<td class="org-right">$$2^1$$</td>
<td class="org-right">$$2^0$$</td>
<td class="org-right">$$2^{-1}$$</td>
<td class="org-right">$$2^{-2}$$</td>
</tr>


<tr>
<td class="org-left">Valeur déc.</td>
<td class="org-right">4</td>
<td class="org-right">2</td>
<td class="org-right">1</td>
<td class="org-right">1/2</td>
<td class="org-right">1/4</td>
</tr>


<tr>
<td class="org-left">Bit</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
</tr>
</tbody>
</table>




## Opérations arithmétiques binaires

Il est possible de transposer les opérations arithmétiques habituelles
pour effectuer différentes opération arithmétiques: addition,
soustraction, multiplication, division, avec des nombres
binaires. Nous verrrons plus loin comment ces opérations s'exécutent
lorsque nous aurons établi les formes d'encodages binaires qui seront
utilisés pour les nombres, notamment la représentation des nombres
signés.




### Multiplication et division par deux

Pour multiplier un nombre binaire non signé par deux, il suffit de
décaler tous ses bits d'une position vers la gauche. Si le nombre est
entier, on devra insérer un zéro à la position zéro. Si le nombre est
fractionnaire, bit le plus significatif de la partie fractionnaire se
retrouvera à la position zéro.

$$ (10011)2 \times 2 = (100110)2 $$
$$ (100,11)2 \times 2 = (1001,1)2 $$

Pour diviser un nombre binaire par deux, il suffit de décaler tous ses
bits d'une position vers la droite. Une division fractionnaire
produira possiblement un nombre fractionnaire, comme dans l'exemple
suivant.

1.  Division fractionnaire

	$$ (10011)2 \div 2 = (1001,1)2 $$

2.  Division entière

	Pour une division entière (sans fraction), on éliminera le bit qui
	aurait été placé après la virgule.
    
	$$ (10011)2 \div 2 = (1001)2 $$
    
	Il est évident de généraliser ces opérations pour les multiplications
	ou divisions par des puissances de 2: par 4, 8, 16, etc.

