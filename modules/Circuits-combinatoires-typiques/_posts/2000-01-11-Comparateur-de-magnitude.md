---
title: Comparateur de magnitude
---

## Comparateur de magnitude

Comparer la magnitude de deux nombres binaires est une opération qui
peut se systématiser, comme on l'a fait pour l'addition. Considérons
deux nombres binaires non-signés, $$A$$ et $$B$$ de même taille $$n$$,
avec leurs bits respectifs $$a_i$$ et $$b_i$$. On veut que notre
comparateur active une de trois sorties, selon le cas: $$A < B$$, $$A
= B$$ ou $$A > B$$. Pour illustrer, nous considérerons $$n = 4$$.

$$ a_3 a_2 a_1 a_0 $$

$$ b_3 b_2 b_1 b_0 $$

Nous aurons besoin d'une fonction qui permet de déterminer si deux
bits sont égaux. Cette fonction correspond à la fonction **équivalence**
ou NOR-exclusif $$a_i b_i + a_i^\prime b_i^\prime $$.  Si les bits
diffèrent en position $$i$$, $$a_i = 1$$ nous permet de conclure que
$$A > B$$, et, à l'inverse, $$a_i = 0 $$ nous indique que $$A < B$$. Nous avons ainsi
les éléments qui permettent d'effectuer une comparaison pour un bit,
comme on peut en voir l'implémentation sur la figure suivante.

![img]({{site.baseurl}}/img/comparateur.svg "Comparateur de magnitude")
*Comparateur de magnitude*

Notre démarche de conception pour $$n$$ bits sera calquée sur la
procédure que nous utilisons intuitivement pour faire une telle
comparaison. La comparaison commence au niveau du bit le plus
significatif. Si ces bits sont égaux, on considère la position
suivante, jusqu'à atteindre une position $$i$$ où les bits diffèrent
ou la fin des nombres $$i=0$$. Si les bits diffèrent en position
$$i$$, $$a_i = 1$$ nous permet de conclure que $$A > B$$, alors que $$a_i = 0
$$ nous indique que $$A < B$$.

Les signaux intermédiaires $$x_i = a_i b_i + a_i^\prime b_i^\prime $$
qui indiquent si deux bits d'une position sont égaux seront mis à
profit pour alimenter un réseau de conditions en forme somme de
produit qui mettront en application les règles énoncées. Les signaux
de sortie binaires sont $$ (A = B), (A < B), (A > B) $$.  D'une part,
la régularité des opérations simplifie la conception et, d'autre part,
l'implémentation sera simplifiée du fait que certains des termes
nécessaires peuvent être réutilisés.

$$ (A = B) = x_3 x_2 x_1 x_0 $$ 

$$ (A < B) = a_3^\prime b_3 + x_3  a_2^\prime b_2  +  x_3 x_2  a_1^\prime b_1 +  x_3 x_2 x_1  a_0^\prime b_0 $$

$$ (A > B) = a_3 b_3^\prime + x_3  a_2 b_2^\prime  +  x_3 x_2  a_1 b_1^\prime +  x_3 x_2 x_1  a_0 b_0^\prime $$

![img]({{site.baseurl}}/img/comparateur_4b.svg "Comparateur de magnitude 4 bits")
*Comparateur de magnitude 4 bits*
