---
title: Logique binaire
---

# Logique binaire

La logique binaire associe une valeur de vérité à des variables, selon
une convention préétablie. Ces valeurs de vérité sont binaires, à
savoir, **vrai** ou **faux**. Pour représenter ces valeurs de vérité, on
peut utiliser un encodage binaire, comme par exemple

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Valeur de vérité</th>
<th scope="col" class="org-right">Valeur binaire</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">Vrai</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">Faux</td>
<td class="org-right">0</td>
</tr>
</tbody>
</table>


## Variable binaire

Une variable binaire, dénotée par une lettre, permet de désigner une
valeur binaire pouvant assumer une de deux valeurs possible, 0
ou 1. La variable est typiquement associée à une proposition, l'état
d'un élément ou toute autre condition pouvant admettre deux états
distincts. En assignant une valeur binaire à la variable, on définit
une valeur de vérité associée à cette variable, et ainsi à la
condition qu'elle représente. Par exemple, soit $$S$$ une variable
binaire qui représente la proposition «le soleil est visible». Alors,
$$S=0$$ peut s'interpréter comme «le soleil est visible est faux» ou
«le soleil n'est pas visible».


## Opérations logiques

Trois opérations logiques de base permettent d'agir sur des variables
binaires, de les combiner et de formuler des expressions logiques à
partir d'elles.

1.  ET: cette opération est représentée (comme la multiplication) par
    un point central ou par l'absence de signe d'opérateur entre les
    arguments. Par exemple, $$x \cdot y$$. La valeur de l'expression est
    1 si et seulement si toutes les variables ont la valeur 1. Sinon,
    la valeur est 0.
2.  OU: cette opération est représentée (comme l'addition) par un signe
    +. Par exemple, $$x + y$$. La valeur de l'expression est 1 si au
    moins une des variables a la valeur 1. Si aucune des variable ne
    vaut 1, la valeur de l'expression est 0.
3.  NON: cette opération est représentée par un prime, comme par
    exemple $$x \prime$$, ou par une barre au-dessus de la variable
    $$\overline{x}$$.  L'opération NON renverse la valeur binaire de son
    argument: si $$x =0$$ alors $$x \prime = 1$$; si $$x =1$$ alors $$x
       \prime = 0$$. Cette opération de négation, est aussi appelée
    complément, car complémenter une valeur binaire revient à faire
    basculer sa valeur.


## Expression logique

Une expression logique combine des variables logiques et des
opérations, et peut donc assumer une valeur binaire logique. Cette
valeur logique peut être assignée à une autre variable, en créant
ainsi une équation logique. Par exemple, $$z = x \cdot y$$ signifie
que $$z$$ assume la valeur de l'expression $$x \cdot y$$. À partir des
valeurs logiques des variables (entrées) $$x$$ et $$y$$, on peut donc
déterminer la valeur logique de la sortie $$z$$.


## Tableaux de vérité

Une façon de décrire la valeur logique d'une variable de sortie en
fonction des valeurs possibles des variables d'entrée est au moyen
d'un tableau de vérité. Dans un tel tableau, il y a une ligne pour
chaque combinaison possible des valeurs d'entrée, et sur chaque ligne,
on indique la valeur de sortie correspondante. C'est en quelque sorte
une description en extension de la valeur de l'expression de sortie.

Voici par exemple les tableaux de vérité pour les opérations de base.


Opération ET:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">\(x\)</th>
<th scope="col" class="org-right">\(y\)</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">\(x \cdot y\)</th>
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
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">1</td>
</tr>
</tbody>
</table>

Opération OU:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">\(x\)</th>
<th scope="col" class="org-right">\(y\)</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">\(x + y\)</th>
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

Opération complément:

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right">\(x\)</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-right">\(x^{\prime}\)</th>
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

