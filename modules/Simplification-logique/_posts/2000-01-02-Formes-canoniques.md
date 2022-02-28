---
title: Formes canoniques
---

# Expressions équivalentes

Un des aspects ennuyeux avec les expressions logiques est que la
correspondance entre expression et fonction logique n'est pas
biunivoque: plusieurs expressions différentes peuvent correspondre à
une seule et même fonction. De plus, certaines des expressions
équivalentes peuvent être plus complexes que d'autres. Lorsque vient
de temps d'implémenter avec des portes une fonction logique, il est la
plupart du temps plus efficace d'implémenter selon un expression plus
simple, voir minimale. On doit donc considérer des approches
systématiques pour simplifier les expressions logiques.

Quand une expression Booléenne est implémentée avec des portes
logiques, chaque terme nécessite une porte et chaque variable au sein
d'un terme correspond à une entrée de la porte. On appelle **littéral**
une variable qui apparaît dans un terme, sous forme complémentée ou
non. Par exemple, l'expression $$F = x^\prime y^\prime z + xz +
xy^\prime z $$ compte huit littéraux. Si on réduit le nombre de
termes, le nombre de littéraux, ou les deux, on obtiendra une
expression qui sera plus simple à implémenter avec des portes.


# Formes canoniques


## Minterms et maxterms

Dans une expression, une variable $$x$$ peut apparaître telle qu'elle
$$x$$ ou complémentée $$x^\prime$$. Si on considère les combinaisons
possibles de deux variables via un opérateur ET, on a alors quatres
possibilités: $$x^\prime y^\prime, x^\prime y, x y^\prime,x
y$$. Chacun de ces quatres termes s'appelle un **minterm**.

De façon générale, pour $$n$$ variables, on aura $$2^n$$ minterms
différents possibles.

De façon équivalente (duale, en vérité), $$n$$ variables reliées par
une fonction OU peuvent donner lieu à $$2^n$$ termes distincts,
appelés **maxterms**. Dans le OU d'un maxterm, une variable est 
telle qu'elle si le bit correspondant est 0 et complémentée si le bit
est 1. Chaque maxterm est le complément du minterm correspondant, et
*vice versa*.

Dans le tableau [18](#orgf76f003), on utilise pour les minterms les
symboles de la forme $$m_j$$ avec $$j$$ qui est l'équivalent décimal
de la combinaison de bits correspondante. Les maxterms sont dénotés
$$M_j$$.

<table id="orgf76f003" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 18 :</span> Minterms et maxterms pour trois variables</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">$$x$$</th>
<th scope="col" class="org-right">$$y$$</th>
<th scope="col" class="org-right">$$z$$</th>
<th scope="col" class="org-left">Minterm</th>
<th scope="col" class="org-left">Symb.</th>
<th scope="col" class="org-left">Maxterm</th>
<th scope="col" class="org-left">Symb.</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">$$x^\prime y^\prime z^\prime$$</td>
<td class="org-left">$$m_0$$</td>
<td class="org-left">$$x+ y+ z$$</td>
<td class="org-left">$$M_0$$</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">$$x^\prime y^\prime z$$</td>
<td class="org-left">$$m_1$$</td>
<td class="org-left">$$x+ y+ z^\prime$$</td>
<td class="org-left">$$M_1$$</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">$$x^\prime y z^\prime$$</td>
<td class="org-left">$$m_2$$</td>
<td class="org-left">$$x+ y^\prime+ z$$</td>
<td class="org-left">$$M_2$$</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">$$x^\prime y z$$</td>
<td class="org-left">$$m_3$$</td>
<td class="org-left">$$x+ y^\prime+ z^\prime$$</td>
<td class="org-left">$$M_3$$</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">$$x y^\prime z^\prime$$</td>
<td class="org-left">$$m_4$$</td>
<td class="org-left">$$x^\prime+ y+ z$$</td>
<td class="org-left">$$M_4$$</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">$$x y^\prime z$$</td>
<td class="org-left">$$m_5$$</td>
<td class="org-left">$$x^\prime+ y+ z^\prime$$</td>
<td class="org-left">$$M_5$$</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">$$x y z^\prime$$</td>
<td class="org-left">$$m_6$$</td>
<td class="org-left">$$x^\prime+ y^\prime+ z$$</td>
<td class="org-left">$$M_6$$</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">$$x y z$$</td>
<td class="org-left">$$m_7$$</td>
<td class="org-left">$$x^\prime + y^\prime+ z^\prime$$</td>
<td class="org-left">$$M_7$$</td>
</tr>
</tbody>
</table>

Pour la fonction $$F_1$$,


<table id="orgee31b82" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 19 :</span> Fonction de trois variables</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">\(x\)</th>
<th scope="col" class="org-right">\(y\)</th>
<th scope="col" class="org-right">\(z\)</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">\(F_1\)</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
</tr>
</tbody>
</table>

on peut donc écrire

$$ F_1 = x y^\prime
z^\prime + x y^\prime z^\prime + x y^\prime z + x y z^\prime + x y z =
m_2 + m_4 + m_5 + m_6 + m_7 $$

puisque ce sont les termes pour lesquels la fonction vaut 1. Cette
forme d'expression est une forme canonique appelée **somme de
produits**.

Pour simplifier la notation, on peut écrire de façon plus compacte  

$$F_1 = \sum (2, 4, 5, 6, 7)$$

Si on veut exprimer le complément d'une fonction, on peut lire dans le
tableau de vérité les combinaisons pour lesquelles la fonction
vaut 0. En prenant un minterm pour chaque combinaison où la fonction
vaut 0 et en faisant un OU de ces termes, on obtient l'expression pour
le complément de la fonction. Ainsi, pour la fonction $$F_1^\prime$$,
on a

$$ F_1^\prime = m_0 + m_1 + m_3 = x^\prime y^\prime z^\prime +
x^\prime y^\prime z + x^\prime y z $$

Si on complémente $$F_1^\prime$$, on obtiendra naturellement
$$F_1$$. En appliquant le théorème de DeMorgan à chaque terme, on
trouve

$$F_1 = (x+ y+ z)(x + y + z^\prime)(x + y^\prime + z^\prime) = M_0
\cdot M_1 \cdot M_3 $$

Cette forme d'expression est aussi une forme canonique appelée
**produit de sommes**.

Pour simplifier la notation, on peut écrire de façon plus compacte 

$$F_1 = \prod (0,1,3)$$


## Somme de produits

Pour $$n$$ variables binaires, on a $$2^n$$ minterms différents
possibles. Les minterms qui participent à la somme dans l'expression
en forme canonique *somme de produits* sont ceux qui produisent un 1
dans le tableau de vérité de la fonction. Puisque la fonction peur
valoir 0 ou 1 pour chaque minterm, le nombre total de fonctions
différentes qui peuvent être définies avec $$n$$ variables est de $$2^{2n}$$.

Si on veut convertir en forme canonique somme de produit l'expression
pour une fonction qui ne serait pas sous cette forme, on commence par
faire l'expansion de l'expression en forme *somme de produits*. Ensuite,
on vérifie chaque terme pour voir si toutes les variables en font
partie. S'il manque une ou des variables, on peut faire un ET du
terme avec une expression du type $$x + x^\prime$$ dans laquelle $$x$$
est une variable manquante. Ce ET ne change pas la valeur de la
fonction puisque $$x + x^\prime = 1$$.

Évidemment, on peut toujours trouver la formulation en forme canonique
en se basant sur le tableau de vérité.


## Produits de sommes

Si on veut convertir en forme canonique *produit de sommes* l'expression
pour une fonction qui ne serait pas sous cette forme, on commence par
faire l'expansion de l'expression en forme *somme de produits*. On peut
avantageusement faire appel à la distributivité de $$+$$ sur $$\cdot$$
pour ce faire. Ensuite, on vérifie chaque terme pour voir si toutes
les variables en font partie. S'il manque une ou des variables, on
peut faire un OU du terme avec une expression du type $$x \cdot
x^\prime$$ dans laquelle $$x$$ est une variable manquante. Ce OU ne
change pas la valeur de la fonction puisque $$x \cdot x^\prime = 0$$.


## Conversion entre formes canoniques

Prenons notre exemple précédent $$F_1 = \sum (2, 4, 5, 6, 7)$$. On sait que $$F_1^\prime = \sum (0,1,3)$$. Si on prend le complément de $$F_1^\prime$$ par le théorème de DeMorgan, on obtient $$F_1 = (m_0 + m_1 + m_3)^\prime = m_0^\prime \cdot m_1^\prime \cdot  m_3^\prime = M_0 \cdot M_1 \cdot M_3  = \prod (0,1,3) $$.

En effet, de minterm à maxterm, on a $$m_j^\prime = M_j$$. Le maxterm d'indice $$j$$ est le complément du minterm de même indice  $$j$$, et vice versa.


## Formes standard

Les expressions canoniques en *somme de produits* et en *produit de
sommes* ne sont généralement pas simples, car toutes les variables
doivent être présentes. Pour l'implémentation, on cherchera des
expressions en formes *somme de produits* ou *produit de sommes* dans
lesquelles les termes pourront être simplifiés. C'est-à-dire que les
termes pourront comporter une, deux, trois, etc. variables plutôt
qu'obligatoirement **toutes** les variables. Toujours pour notre
fonction exemple, on peut écrire

$$F_1 = x + y z^\prime$$

Lorsqu'on implémente une telle fonction avec des portes logiques, il
faut une porte ET pour chaque terme produit (qui comporte plus d'une
variable) et une porte OU pour faire la somme finale. On obtient une
implémentation à deux niveaux.

De façon duale, on peut également obtenir une formulation en produit
de somme qui aboutira à une implémentation à deux niveaux avec une
porte OU par terme et une porte ET pour le produit final.

