# Nombres binaires

Les nombres binaires sont essentiellement construits de la même façon
que les nombres décimaux avec lesquels nous sont plus familiers. La
différence fondamentale tient au fait qu'il n'est possible d'utiliser
que deux symboles (chiffres), 0 et 1, plutôt que les dix chiffres de 0
à 9. Les chiffres sont nommées bits (contraction de **b** inary dig
**it**).

Par exemple, le nombre décimal que nous écrivons $$2843$$ correspond à
$$2 \times 1000 + 8 \times 100 + 4 \times 10 + 3 \times 1$$. Il s'agit
d'un système positionnel, dans lequel la valeur attribuée à un chiffre
est définie par sa position et par la valeur de la **base** du système
de numération. Ainsi, pour ce nombre décimal, la base vaut 10 et on a
$$2 \times 10^3 + 8 \times 10^2 + 4 \times 10^1 + 3 \times 10^0$$. La
position la plus à gauche est celle dont la valeur est la plus
grande. C'est le **chiffre le plus significatif**; la position de droite
correspond au **chiffre le moins significatif**. On peut imaginer une
virgule après le chiffre le moins significatif, pour délimiter la
partie entière du nombre. D'autres chiffres, placés à droite de cette
virgule correspondraient à la partie fractionnaire. On y reviendra.

Les mêmes règles positionnelles permettent d'attribuer une valeur à un
nombre binaire, en tenant compte du fait que la base vaut cette
fois-ci 2. Par exemple, la valeur attribuée au nombre binaire
$$10101$$ est 

$$ 1 \times 2^4 + 0 \times 2^3 + 1 \times 2^2 + 0 \times 2^1 + 1
\times 2^0 = 16+4+1= 21 $$,

comme on peut voir dans le tableau [1](#org9d95b45).

<table id="org9d95b45" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 1 :</span> Valeur binaire du nombre $$10101$$</caption>

<colgroup>
<col  class="org-left" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<tbody>
<tr>
<td class="org-left">Position</td>
<td class="org-right">4</td>
<td class="org-right">3</td>
<td class="org-right">2</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">Valeur</td>
<td class="org-right">$$2^4$$</td>
<td class="org-right">$$2^3$$</td>
<td class="org-right">$$2^2$$</td>
<td class="org-right">$$2^1$$</td>
<td class="org-right">$$2^0$$</td>
</tr>


<tr>
<td class="org-left">Valeur déc.</td>
<td class="org-right">16</td>
<td class="org-right">8</td>
<td class="org-right">4</td>
<td class="org-right">2</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">Bit</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
</tr>
</tbody>
</table>

Nous avons ici le **bit le plus significatif** à gauche et le **bit le
moins significatif** à droite. Chaque chiffre vaut 2 fois plus que le
chiffre immédiatement placé à sa droite.


# Conversion binaire <-> décimal

Convertir un nombre entier binaire en nombre décimal se fait
naturellement, en s'appuyant sur les valeurs associées à la notation
positionnelle. La conversion en sens inverse, de décimal à binaire,
est un peu moins évidente. La méthode consiste à faire une division
entière du nombre (et des quotients successifs) par 2 et à noter les
restes obtenus. Le premier reste correspond au bit le moins
significatif, et le dernier au bit le plus significatif.

Par exemple, les opération pour convertir 37 en binaire sont résumées
dans le tableau [2](#org26bffc8).

<table id="org26bffc8" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 2 :</span> Étapes de conversion de 37 en binaire</caption>

<colgroup>
<col  class="org-left" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">Quotient entier</th>
<th scope="col" class="org-right">Reste</th>
<th scope="col" class="org-left">Coefficient</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">37/2</td>
<td class="org-right">18</td>
<td class="org-right">1</td>
<td class="org-left">$$a_0 = 1$$</td>
</tr>


<tr>
<td class="org-left">18/2</td>
<td class="org-right">9</td>
<td class="org-right">0</td>
<td class="org-left">$$a_1 = 0$$</td>
</tr>


<tr>
<td class="org-left">9/2</td>
<td class="org-right">4</td>
<td class="org-right">1</td>
<td class="org-left">$$a_2 = 1$$</td>
</tr>


<tr>
<td class="org-left">4/2</td>
<td class="org-right">2</td>
<td class="org-right">0</td>
<td class="org-left">$$a_3 = 0$$</td>
</tr>


<tr>
<td class="org-left">2/2</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">$$a_4 = 0$$</td>
</tr>


<tr>
<td class="org-left">1/2</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">$$a_5 = 1$$</td>
</tr>
</tbody>
</table>

On obtient ainsi 100101.

### Conversion en sens inverse

La conversion de octal (respectivement, hexadécimal) à binaire se fait
simplement en remplaçant chaque chiffre octal (resp. hexadécimal) par
le groupe de trois (resp. quatre) bits correspondant, en partant du
moins significatif.
