---
title: Compléments de nombres
---

# Compléments de nombres

Les compléments de nombres jouent un rôle dans la simplification de
certaines opérations mathématiques et logiques. Dans un système de
numération de base $$b$$, on considère deux types de compléments: le
complément à $$b$$ et le complément à $$b-1$$. Pour la base 10, nous
aurons donc le complément à dix et le complément à neuf. Pour les nombres
binaires (base 2), on aura le complément à deux et le complément à un. 
Pour évaluer les compléments, on doit tenir compte du nombre de
chiffres que comportent lescomposant le nombre.

## Complément à neuf et complément à un

Soit un nombre entier $$N$$ en base $$b$$ constitué de $$n$$ chiffres. Le
complément à $$b-1$$ de $$N$$ est $$(b^n-1)-N$$.

Par exemple, en base $$b=10$$, le complément à neuf pour le nombre décimal
$$N = 4576$$ formé de $$n=4$$ chiffres sera $$(b^n-1)-N = (10^4 -1) -
4576 = 5424 $$.

En base $$b=2$$, le complément à un pour le nombre binaire $$N =
(10011)2 = (19)10 $$ formé de $$n=5$$ bits sera $$(b^n-1)-N = (2^5
-1) - 19 = 12 $$ ce qui donne en binaire: $$(12)10 = (1100)2 $$.

On peut vérifier qu'il est très facile, en binaire, de déterminer le
complément à un, sans effectuer de calculs, en inversant simplement
chacun des bits de la représentation binaire du nombre à
complémenter. Ainsi, avec notre exemple, on trouve:

$$ 10011 $$

$$ 01100 $$

Remarquons ici un zéro non significatif comme premier bit à gauche.


## Complément à un et complément à deux

Le complément à $$b$$ de l'entier $$N$$ s'évalue comme
$$(b^n)-N$$. Cela correspond à ajouter 1 au complément à $$b-1$$.

Ainsi pour notre exemple précédent en base $$b=10$$, le complément à un pour le nombre
décimal $$N = 4576$$ formé de $$n=4$$ chiffres sera $$(b^n)-N =
(10^4) - 4576 = 5425 $$.

Pour notre autre exemple, en base $$b=2$$, le complément à deux pour
le nombre binaire $$N = (10011)2 = (19)10 $$ formé de $$n=5$$ bits
sera $$(b^n)-N = (2^5) - 19 = 13 $$ ce qui donne en binaire:
$$(13)10 = (1101)2 $$.

L'évaluation directe à la main, sans calculs, du complément à deux est également
possible en suivant la démarche suivante:

1.  On parcourt le nombre binaire initial à partir (à droite) du bit le moins
    significatif, et on retranscrit les bits rencontrés jusqu'à
    atteindre un premier bit 1, que l'on retranscrit également.
2.  On continue la retranscription vers la gauche, en inversant cette
    fois les bits subséquents.

Par exemple, pour (10110)2, on aura la démarche détaillée dans le
tableau [8](#org6c42995). Les étapes sont numérotées selon la position
considérée, à partir de la droite.

<table id="org6c42995" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 8 :</span> Étapes pour complément à deux</caption>

<colgroup>
<col  class="org-left" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">nombre</th>
<th scope="col" class="org-right">1</th>
<th scope="col" class="org-right">0</th>
<th scope="col" class="org-right">1</th>
<th scope="col" class="org-right">1</th>
<th scope="col" class="org-right">0</th>
<th scope="col" class="org-left">&#xa0;</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">Étape 0</td>
<td class="org-right">&#xa0;</td>
<td class="org-right">&#xa0;</td>
<td class="org-right">&#xa0;</td>
<td class="org-right">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-left">retranscrit</td>
</tr>


<tr>
<td class="org-left">Étape 1</td>
<td class="org-right">&#xa0;</td>
<td class="org-right">&#xa0;</td>
<td class="org-right">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">retranscrit</td>
</tr>


<tr>
<td class="org-left">Étape 2</td>
<td class="org-right">&#xa0;</td>
<td class="org-right">&#xa0;</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">Inversé</td>
</tr>


<tr>
<td class="org-left">Étape 3</td>
<td class="org-right">&#xa0;</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">Inversé</td>
</tr>


<tr>
<td class="org-left">Étape 4</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">Inversé</td>
</tr>
</tbody>
</table>

Pour une évaluation par un circuit, on commencera par déterminer le
complément à un par inversion et on lui additionnera 1 pour obtenir le
complément à deux.


# Nombres signés et codage

Représenter de nombres $$ \geq 0$$ en binaire est donc relativement
naturel. Dans l'optique où on voudra stocker ces nombres dans une
mémoire binaire numérique, il n'y a qu'à prévoir une taille suffisante
(en nombre de bits) pour pouvoir accommoder des nombres assez grands
pour l'application considérée. Avec $$n$$ bits, il est possible de
représenter des entiers de 0 à $$2^n-1$$.

Mais on peut se demander comment représenter des nombres négatifs $$<
0$$. Une première observation est le fait que si on considère des
nombres positif **et** négatifs, on double en quelque sorte la quantité
de valeurs à représenter. Par exemple, il y a 21 nombres à représenter
si on veut pouvoir utiliser les valeurs comprises entre $$-10$$ et
$$+10$$, comme on peut le voir dans le tableau [9](#orgfd9f2e2).

<table id="orgfd9f2e2" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 9 :</span> Nombre de valeurs à représenter entre $$-10 \mbox{ et } +10$$</caption>

<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Gamme</th>
<th scope="col" class="org-right">n. de valeurs</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">de -10 à -1</td>
<td class="org-right">10</td>
</tr>


<tr>
<td class="org-left">0</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">de 1 à 10</td>
<td class="org-right">10</td>
</tr>
</tbody>

<tbody>
<tr>
<td class="org-left">Total</td>
<td class="org-right">21</td>
</tr>
</tbody>
</table>

Nous devons donc nous assurer d'avoir autant de combinaisons de bits qu'il
sera nécessaire. La deuxième observation est qu'il faudra un moyen de
distinguer les nombres positifs des nombres négatifs. Si on veut que
cette distinction puisse se faire non seulement sur papier, mais
surtout lorsque les nombres seront stockés et manipulés dans un
système électronique, il faut définir un format binaire «tout compris»
qui permette de le faire.

Nous devons donc établir **code**, c'est-à-dire, une **convention** qui
permettra de donner un sens à un groupe de bits. Le choix de la
convention devrait être guidé par les usages qui seront ultimement
faits des nombres qui seront représentés.

En fait, lorsque nous avons convenu (implicitement) de représenter des
nombres entiers en utilisant directement la conversion en base 2 des
nombres décimaux, nous avons établi un code de représentation, qui,
bien que naturel, n'en est pas moins une convention. Ici, nous devrons
formuler plus explicitement la convention qui sera utilisée pour
représenter les entier signés.

Une convention de représentation peut être établie totalement
arbitrairement, mais elle sera sans doute plus utile si elle peut
contribuer à faciliter des opérations courantes réalisées avec les
éléments à représenter. Puisqu'il est question ici de nombre entiers
signés, l'opération à considérer en priorité est l'addition. On
devrait aussi considérer les trois points suivants dans notre choix de
convention pour attribuer des codes binaires aux valeurs. (Pour
illustrer notre réflexion, nous allons considérer des nombre pouvant
être représentés par des codes binaires de quatre bits, ce qui permet
en théorie de représenter un total de 16 valeurs.)

1.  Puisqu'il faudra partager notre ensemble de codes binaires en deux,
    il serait logique de placer la représentation pour zéro au centre
    de ce découpage.

2.  Les codes binaires utilisés pour un nombre et son inverse additif
    devraient être disposés symétriquement autour du code utilisé pour
    représenter le zéro. Il est naturel de représenter la valeur zéro
    avec le code 0000.

3.  L'ordre des codes devrait correspondre à l'ordre des nombres. On
    sait bien comment ordonner les nombres entiers, en passant des
    nombres négatifs aux nombres positifs.

Quel ordre serait approprié pour les représentations (codes binaires)?
L'ordre naturel, du moins pour les nombres entiers positifs, serait de
passer de 0000 à 0001 à 0010, etc. Il faudra cependant limiter le
nombre de valeurs positives, car il faut réserver des codes pour les
valeurs négatives, et nous avons déjà utilisé un code pour le
zéro. 

Quel code binaire devrait-on placer juste avant le zéro, pour
représenter -1? Si on dispose l'ensemble des codes binaires entre 0000
et 1111 selon un cycle, tel qu'illustré sur la figure suivante,
alors le code approprié pour -1 sera 1111. Et le code pour -2
sera 1110. Un avantage de cette disposition est que, en ajoutant 1
pour passer de -2 à -1, on parcourt le cycle dans le même sens qu'en
ajoutant 1 pour passer de 1 à 2.


![img]({{site.baseurl}}/img/cycle.png "Relations entre les codes dans l'assignation en complément à deux"){:id="org0ae272e"}
*Relations entre les codes dans l'assignation en complément à deux*


En suivant cette logique, on pourra, comme indiqué sur la figure,
assigner les codes en jaune à des valeurs positives et les codes en
vert à des valeurs négatives. Si on assigne autant de valeur positives
que de valeurs négatives, un seul code binaire ne sera pas utilisable,
le code 1000. Tout déplacement selon le sens des flèches correspond à
une addition; tout déplacement en sens inverse correspond à une
soustraction. Les nombres binaires seront ainsi symétriques par
rapport à notre zéro.

Nous obtenons ainsi l'assignation du tableau [10](#org86e68b2).

<table id="org86e68b2" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 10 :</span> Assignation de codes aux nombres de 4 bits</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">Code</th>
<th scope="col" class="org-right">Nombre</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">1001</td>
<td class="org-right">-7</td>
</tr>


<tr>
<td class="org-right">1010</td>
<td class="org-right">-6</td>
</tr>


<tr>
<td class="org-right">1011</td>
<td class="org-right">-5</td>
</tr>


<tr>
<td class="org-right">1100</td>
<td class="org-right">-4</td>
</tr>


<tr>
<td class="org-right">1101</td>
<td class="org-right">-3</td>
</tr>


<tr>
<td class="org-right">1110</td>
<td class="org-right">-2</td>
</tr>


<tr>
<td class="org-right">1111</td>
<td class="org-right">-1</td>
</tr>


<tr>
<td class="org-right">0000</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0001</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">0010</td>
<td class="org-right">2</td>
</tr>


<tr>
<td class="org-right">0011</td>
<td class="org-right">3</td>
</tr>


<tr>
<td class="org-right">0100</td>
<td class="org-right">4</td>
</tr>


<tr>
<td class="org-right">0101</td>
<td class="org-right">5</td>
</tr>


<tr>
<td class="org-right">0110</td>
<td class="org-right">6</td>
</tr>


<tr>
<td class="org-right">0111</td>
<td class="org-right">7</td>
</tr>


<tr>
<td class="org-right">1000</td>
<td class="org-right">aucun</td>
</tr>
</tbody>
</table>

Voici quelques observations importantes sur cette représentation.

1.  Tous les codes des nombres négatifs ont le premier bit à gauche
    (qui serait le bit le plus significatif) à la valeur 1, alors que
    les autres ont codes ont la valeur 0. Ce bit peut ainsi servir
    d'indicateur de signe, avec la convention habituelle qu'on ne met
    pas de signe au zéro. On parlera ainsi de **bit de signe** pour
    dénoter ce bit, qui ne contribue pas à la grandeur (en valeur
    absolue) du nombre.

2.  L'inverse additif d'un nombre $$n$$, c'est-à-dire $$-n$$, est
    représenté par le **complément à deux** du nombre. Ceci signifie que
    pour trouver l'inverse additif d'un nombre, il suffit de calculer
    son complément à deux. Le complément à deux du complément à deux nous
    re-donnera le nombre initial, conformément à la double négation
    $$--n = n$$.


Il existe d'autres conventions pour la représentation de nombres
signés, comme par exemple, la représentation signe+magnitude, mais la
représentation en complément à deux est de loin la plus utilisée.


# Opérations arithmétiques binaires


## Addition de nombres non signés

En transposant les opérations classiques pour effectuer à la main des
additions ou des soustractions, il est possible d'effectuer des
calculs avec des nombres binaires. Additionner des nombres entier non
signés ne pose pas de difficultés particulières.

On suppose deux nombre entiers binaires non signés $$A$$ et $$B$$
représentés en utilisant le même nombre de bits (si un nombre est plus
petit, on ajoutera des 0 non significatifs à gauche pour compléter la
représentation). Lorsqu'on effectue l'opération bit par bit, en
partant de la position la moins significative, on peut utiliser la
table d'addition suivante. À la position $$i$$, on a trois entrées à
prendre en considération: $$A_{i}$$ et $$B_{i}$$, les bits des nombres
à additionner et $$R_{i-1}$$, la retenue provenant de la position
$$i-1$$. En sortie, on a la somme $$S_{i}$$ et la retenue $$R_{i}$$.

<table id="org5734de2" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 11 :</span> Tableau de vérité pour l'additionneur binaire</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$A_{i}$$</th>
<th scope="col" class="org-right">$$B_{i}$$</th>
<th scope="col" class="org-right">$$R_{i-1}$$</th>
<th scope="col" class="org-right">$$R_{i}$$</th>
<th scope="col" class="org-right">$$S_{i}$$</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
</tr>
</tbody>
</table>

Exemple:

A: 101110001
B: 001111001
S: 111101010
R: 001110001

S'il y a une retenue non nulle à la suite de l'addition à la position
la plus significative, il y a un **débordement**, car le résultat est trop
grand pour être représenté avec le nombre de bits initial.


## Addition de nombres signés

L'addition de nombre signés codés avec la représentation en complément
à deux est nettement avantageuse. Il suffit d’additionner les deux
nombres comme s'il s'agissait de nombre non signés, en incluant les
bits de signe dans le calcul. La retenue qui émane de la position la
plus significative ne doit pas être prise en compte. 

Exemple 1:

Additionnons A=-2 et B=4, représentés respectivement (1110)2 et (0100)2.

A: 1110
B: 0100
S: 0010
R: 1100

qui nous donne bien le résultat escompté: S = (0010)2 = (2)10.

Exemple 2:

Additionnons A=3 et B=-5, représentés respectivement (0011)2 et (1011)2.

A: 0011
B: 1011
S: 1110
R: 0011

qui nous donne bien le résultat escompté: S = (1110)2 = (-2)10.

On peut vérifier facilement qu'additionner un nombre avec son
complément à deux donne toujours zéro, ce qui correspond à faire $$-n + n
= 0$$.

Comme avec l'addition de nombre entiers non signés, il faudra se
préoccuper des débordements qui peuvent survenir parce que la capacité
de représentation est limitée par la taille (en nombre de bits) des
codes binaires utilisés.


## Soustraction de nombres signés

La soustraction s'effectue en faisant $$ A - B = A + (-B) $$, comme suit:

1.  On détermine le complément à deux du nombre à soustraire.
2.  On additionne ce complément à deux au nombre duquel on soustrait. La
    retenue qui émane de la position la plus significative ne doit pas
    être prise en compte.

Le résultat s'interprétera comme un nombre signé en complément à deux. 


# Codes binaires

Il n'y a pas que des nombres que l'on voudra représenter en
binaire. Il est maintenant le temps de définir ce qu'on appelle un
**code binaire**, car cette notion est au centre de tous les encodages
que nous aurons à utiliser.

Un code binaire sur $$n$$ bits est typiquement une association entre,
d'une part, les éléments d'un ensemble que l'on cherche à représenter
et d’autre part, les différents groupes ou patrons possibles avec
$$n$$ bits. On appelle parfois ces patrons des mots-code (ou par abus
de langage, des codes). Comme il y a $$2^n$$ patrons de bits
différents, il est possible d'associer jusqu'à ce nombre
d'éléments.

Une règle, souvent implicite mais essentielle, est qu'**on
ne devrait associer qu'un seul élément à un patron de bits donné.**
Sinon, l'interprétation du code (le décodage) devient ambigu. Selon
l'application, il n'est pas toujours nécessaire d'associer tous les
patrons de bits à des éléments. Par exemple, si on veut représenter
les chiffres décimaux, il est nécessaires de disposer d'au moins 10
patrons de bits, ce qui est possible avec $$n=4$$. Puisque $$2^4 =
16$$, il y aura $$16 - 10 = 6$$ patrons de bits inutilisés.

La règle spécifique d'association peut être établie arbitrairement,
mais elle est souvent conçue en vue de respecter certaines propriétés
liées aux éléments à représenter ou à la configuration du code
lui-même. C'est ce qu'on a fait, par exemple, pour définir la
convention d'encodage des entiers par complément à deux.


## Code Gray

Lorsqu'on utilise un code binaire pour représenter des valeurs
associées à des phénomènes physiques, il peut être opportun d’utiliser
un encodage dans lequel le nombre de changements de bits est minimal
lorsqu'on passe d'un patron de bits au suivant dans la séquence des
codes. Par exemple, si on cherche à encoder des positions d'un
interrupteur rotatif (comme pour encoder des angles), il est
préférable que lorsqu'on passe d'un position à la suivante en tournant
le commutateur, un seul bit ne change dans la sortie. Ainsi, une
erreur sur un bit n'introduit pas un gros changement dans
l'interprétation de la valeur encodée. Un code Gray permet d'atteindre
cet objectif.

Avec code Gray du tableau [12](#orgdea8e5e), on peut voir par exemple que la
transition entre les codes pour 7 et 8 n’entraîne qu'un changement sur
un bit, de 0110 à 1100. Avec un encodage classique basé sur les
entiers binaires, on aurait observé pour ce cas une transition entre
0111 et 1000, qui comporte quatre changements de valeurs de bits.

<table id="orgdea8e5e" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 12 :</span> Code Gray à quatre bits</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">Code Gray</th>
<th scope="col" class="org-right">Valeur</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0000</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0001</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">0011</td>
<td class="org-right">2</td>
</tr>


<tr>
<td class="org-right">0010</td>
<td class="org-right">3</td>
</tr>


<tr>
<td class="org-right">0110</td>
<td class="org-right">4</td>
</tr>


<tr>
<td class="org-right">0111</td>
<td class="org-right">5</td>
</tr>


<tr>
<td class="org-right">0101</td>
<td class="org-right">6</td>
</tr>


<tr>
<td class="org-right">0100</td>
<td class="org-right">7</td>
</tr>


<tr>
<td class="org-right">1100</td>
<td class="org-right">8</td>
</tr>


<tr>
<td class="org-right">1101</td>
<td class="org-right">9</td>
</tr>


<tr>
<td class="org-right">1111</td>
<td class="org-right">10</td>
</tr>


<tr>
<td class="org-right">1110</td>
<td class="org-right">11</td>
</tr>


<tr>
<td class="org-right">1010</td>
<td class="org-right">12</td>
</tr>


<tr>
<td class="org-right">1011</td>
<td class="org-right">13</td>
</tr>


<tr>
<td class="org-right">1001</td>
<td class="org-right">14</td>
</tr>


<tr>
<td class="org-right">1000</td>
<td class="org-right">15</td>
</tr>
</tbody>
</table>

## Codes alphanumériques et autres

Vous rencontrerez sans doute plusieurs autres encodages courants,
comme par exemple pour encoder des caractères (code ASCII, codes UTF)
ou pour encoder uniquement des chiffre décimaux (code BCD). Une fois
qu'on a bien compris la règle d'encodage, il n'y a généralement pas de
difficultés à les utiliser.

Certains codes sont construits de manière à permettre d’identifier et
même, dans certains cas, de corriger des erreurs dans le stockage ou
la transmission des données encodées. Ces codes sont construits en
fonction de règles d'encodage, qui, lorsqu'elles ne sont pas
respectées, permettent de constater la présence d'erreurs.

