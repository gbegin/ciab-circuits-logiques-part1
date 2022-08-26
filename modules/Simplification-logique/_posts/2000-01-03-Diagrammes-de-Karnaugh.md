---
title: Diagrammes de Karnaugh
---
# Objectifs de minimisation

Étant donné une fonction logique de $$n$$ variables $$z(x_1, x_2,
 \ldots, x_n)$$, on veut déterminer une expression pour cette fonction
sous la forme *Somme de Produit* (S de P) ou *Produit de Sommes* (P de S)
qui

1.  comporte un nombre minimum de termes produits (pour la forme S de P)
    ou de termes sommes (pour la forme P de S);

2.  est telle qu'aucune expression pour $$z$$ comportant le même nombre
    de termes n'utilise moins de littéraux.

# Diagrammes de Karnaugh

Une méthode visuelle permet de simplifier l'expression logique d'une
fonction en systématisant une procédure faisant appel à un diagramme
qui fait ressortir les simplifications possibles.

Un diagramme de Karnaugh (diag-K) est constitué d'un regroupement de
cellules carrées, chaque cellule correspondant à un minterm
possible. Les cellules sont organisées de façon à ce que lorsqu'on
passe d'une cellule à une cellule adjacente (horizontalement ou
verticalement), un seul bit du minterm change, ce qui revient à dire
qu'une seul variable passe de telle qu'elle à complémentée.

Cela fait en sorte que si la fonction est 1 pour deux minterms
adjacents, la somme des deux minterms pourra être simplifiée en un
seul terme dans lequel la variable correspondant au bit qui change est
absente. Par exemple, on pourrait avoir pour deux minterms adjacents
$$m_5 + m_7 = xy^\prime z + xyz = xz(y^\prime + y) = xz $$. Ici les
deux minterms adjacents diffèrent par la variable $$y$$, qui sera donc
supprimée du terme produit résultant.

![Diag-K à deux variables.]({{site.baseurl}}/img/kmap2.svg "Diag-K à deux variables")
*Diag-K à deux variables*


![Diag-k à trois variables, avec minterms.]({{site.baseurl}}/img/kmap3minterms.svg "Diag-k à trois variables, avec minterms")
*Diag-k à trois variables, avec minterms*


Sur le diagramme à trois variables, on voit que les bits $$AB$$ sont
ordonnés selon un code Gray, de façon à ce qu'un seul des bits change
lorsqu'on passe d'une cellule à la suivante
horizontalement. L'adjacence se poursuit en bout de diagramme: par
exemple, la cellule 100 ($m_4$) est adjacente horizontalement à la
cellule 000 ($m_0$). On peut imaginer le diagramme comme replié sur
lui-même pour visualiser cette adjacence.

![Diag-K à trois variables.]({{site.baseurl}}/img/kmap3.svg "Diag-K à trois variables")

Sur le diagramme à quatre variables, l'adjacence repliée est autant
horizontale que verticale.

Pour plus de quatre variables, il devient difficile d'utiliser cette
méthode: les diagrammes sont de grande taille et surtout, les règles
d'adjacence ne sont plus aussi facilement observables. Les risques
d'erreurs sont plus grands.

![Diag-K à quatre variables.]({{site.baseurl}}/img/kmap4.svg "Diag-K à quatre variables")
*Diag-K à quatre variables*

## Procédure de simplification

Pour utiliser un diag-K pour minimiser une fonction logique, 

1.  Les minterms de la fonction à minimiser sont identifiés en insérant
    un 1 dans la cellule correspondant à chaque minterm.
2.  On cherche dans le diagramme pour trouver des regroupement de deux
    cellules adjacentes qui sont marquées d'un 1.
3.  Chaque groupe de deux cellules 1 adjacentes est marqué comme
    groupe. Un même minterm peut être incorporé à plus d'un groupe.
4.  Il est aussi possible de regrouper les groupes: deux groupes de 2
    qui sont adjacents peuvent ainsi se regrouper en un groupe
    de 4. Les tailles de groupes doivent être des puissances de 2. Il
    est ainsi possible de créer des groupes de 2, 4, 8 ou 16 minterms.
5.  Une fois tous les regroupements identifiés, il est possible de
    lire l'expression de la fonction en *somme de produits*. Chaque
    groupement correspond à un terme produit, et la ou les variables
    dont le bit ne change pas dans le groupe sont conservées; les
    autres sont éliminées.

Considérons par exemple la fonction $$F(A,B,C) = \sum (0, 4, 6,
7)$$. Après la première étape, on obtient

![Diagramme après l'étape 1.]({{site.baseurl}}/img/kmap3fonct.svg "Diagramme après l'étape 1")

Après les regroupements, on obtient un diag-K comportant trois regroupements

![Diagramme après les regroupements.]({{site.baseurl}}/img/kmap3fonctsimp.svg "Diagramme après les regroupements")

Le groupe en rouge corresond au produit $$B^\prime C^\prime $$, celui
en bleu correspond à $$A B $$ et celui en vert correspond à $$A
C^\prime $$. L'expression finale en *somme de produits* est donc $$F =
B^\prime C^\prime + A B + A C^\prime $$.


## Cas facultatifs

Certaines fonctions sont incomplètement définies, dans le sens où
certaines combinaisons d'entrées ne se produiront jamais ou seront
sans conséquences si elles se produisent. On parle de **cas
indifférents** ou **facultatifs** (en anglais, *don't care*). Pour la
simplification, ces cas pourront être traités tantôt comme des 0,
tantôt comme des 1, selon ce qui sera le plus avantageux.

Pour tenir compte de ces cas, les minterms seront notés avec un X dans
le diagramme de Karnaugh. Dans l'exemple à quatre variables suivant,
sur deux cas facultatifs, un seul, celui correspondant à $$m_{7}$$, a
été traité comme un 1, ce qui a permis de créer le regroupement en
bleu. L'autre cas facultatif, correspondant à $$m_{2}$$, n'a pas servi
dans un regroupement, ce qui signifie qu'il a été traité comme
un 0. La fonction résultante est donc $$A C^\prime D^\prime + BD + AB
$$.

![Diag-K avec cas facultatifs.]({{site.baseurl}}/img/kmap4fonct.svg "Diag-K avec cas facultatifs")




## Impliquants

Le choix des regroupements à utiliser doit toujours viser à s'assurer que:

1.  Tous les minterms de la fonction sont couverts par les
    regroupements choisis.
2.  Le nombre de termes retenus pour l'expression est minimal.
3.  Il n'y a pas de termes redondants, c'est-à-dire, qui couvrent
    uniquement des minterms déjà couverts.

Il y a parfois des plus d'une expression qui rencontre ces
critères. Il est possible de systématiser le choix des termes en
prenant en compte le caractère essentiel des termes.

Soit $$p(X)$$ un terme produit de littéraux tirés de l'ensemble de
variables $$X$$. Si, pour une fonction logique $$z(X)$$ définie pour
le même ensemble de variables, la relation

> pour tout $$A$$ tel que $$p(A)=1$$, $$z(A)=1$$

tient, alors $$p$$ est un **impliquant** de $$z$$. Cela signifie que
la vérité du terme produit $$p$$ implique celle de $$z$$. *Tout
minterm de $$p$$ est aussi un minterm de $$z$$.*

Exemple:

$$z_1 = ab + bc + a b^{\prime} c$$ 

$$a b$$, $$b c$$, $$a b^{\prime} c$$ sont des impliquants évidents de $$z_1$$.

$$a^{\prime} b c$$, $$a b c^{\prime}$$, $$a b c$$, $$a c$$ sont aussi des
impliquants de $$z_1$$.

![Diag-K pour l'exemple des impliquants.]({{site.baseurl}}/img/kmap3fonctimp.svg "Diag-K pour l'exemple des impliquants")
*Diag-K pour l'exemple des impliquants*

## Impliquant premier

Un impliquant $$p$$ de la fonction $$z$$ est **premier** si n'importe quel
terme produit obtenu de $$p$$ en supprimant un littéral n'est pas un
impliquant de $$z$$.

$$a b$$ est un impliquant premier de $$z_1$$ car ni $$a$$ ni $$b$$ ne sont des
impliquants de $$z_1$$.

$$a b^{\prime} c$$ n'est pas un impliquant premier de $$z_1$$ car $$a c$$
est un impliquant de $$z_1$$.

Sur un diagramme de Karnaugh, un impliquant premier (i.p.) est un
groupe qui n'est contenu dans aucun autre groupe plus grand.


## Couverture d'une fonction

Un sous-ensemble d'i.p. qui contient tous les minterms d'une fonction
**couvre** la fonction.

Une **couverture minimale** est une couverture avec

1.  le nombre minimal d'impliquants premiers,

2.  le moins de littéraux parmi les couvertures avec nombre minimum
    d'implicants.


## Impliquant premier essentiel

Un i.p. est **essentiel** si et seulement si il couvre un minterm de la
fonction qui ne peut être couvert par un autre i.p. de la fonction.

Une couverture de la fonction **doit** contenir tous les impliquants
premiers essentiels (i.p.e.).

Un **impliquant premier absolument inessentiel** est un i.p. qui couvre
des minterms qui sont tous couverts par les i.p.e. de la fonction.


## Sélection des impliquants

Règles de sélection des impliquants

1.  Mettre de côté tous les i.p.e. Ils seront utilisés dans la solution
    finale.

2.  Éliminer tous les i.p. absolument inessentiels.

3.  Il reste à choisir parmi les i.p. inessentiels pour obtenir une
    couverture minimale.

Lorsque le problème est de taille réduite, on peut faire une recherche
exhaustive de toutes les solutions possibles pour choisir la solution
minimale.


## Minimisation avec cas facultatifs

1.  Lorsqu'on détermine les i.p., on doit considérer les X comme des
    1, de façon à pouvoir utiliser les i.p. rendus possibles par les
    cas facultatifs.

2.  Lors de la sélection des i.p. pour obtenir une couverture minimale,
    on ne doit pas essayer de couvrir les X.


## Minimisation avec plusieurs fonctions

Si deux fonctions $$z_i$$ et$$z_j$$ ont des expressions minimales qui
comportent un terme commun, une seule porte suffit pour générer ce
terme au profit des deux fonctions.

Exemple:

$$z_1 = a c + a^{\prime} b c^{\prime} + a^{\prime} c^{\prime} d$$

$$z_2 = a c + a^{\prime}  b c^{\prime} d^{\prime} +
a^{\prime} b^{\prime} c^{\prime} d$$

![Fonction z_1.]({{site.baseurl}}/img/kmap4z1.svg "Fonction $$z_1$$")
*Fonction $$z_1$$*

![Fonction z_2.]({{site.baseurl}}/img/kmap4z2.svg "Fonction $$z_2$$")
*Fonction $$z_2$$*

Il est alors préférable de réutiliser les termes communs et de générer
seulement les termes manquants pour la seconde fonction. Dans cet
exemple, le terme $$a c$$ sera calculé une seule fois. Les termes $$
a^{\prime} b c^{\prime} d^{\prime}$$ et $$a^{\prime} b^{\prime} c^{\prime}
d$$ sont nécessaires pour $$z_2$$. Alors, pour $$z_1$$, on fera

$$ z_1 =  a c + a^{\prime}  b c^{\prime} d^{\prime} +
a^{\prime} b^{\prime} c^{\prime} d +
a^{\prime} b c^{\prime} d $$

qui ne nous coûtera que le dernier terme produit et une somme de
quatre termes.


