# Implémentation des fonctions simplifiées

Les circuits logiques simplifiés en forme *produit de sommes* ou
*somme de produits* sont souvent mis en oeuvre au moyen de portes NAND
ou NOR plutôt qu'avec des portes ET et OU. La raison est qu'il est
plus simple en pratique de réaliser ces portes.


## Implémentation à deux niveaux

Une fonction en forme *somme de produits* s'implémente évidemment avec
des portes ET pour les produits et une porte OU pour la somme
finale. Considérons par exemple $$F = AB + CD$$.

![img]({{site.baseurl}}/img/produit_somme.svg "Produit de sommes pour \(F = AB + CD\)") 

La fonction peut aussi s'implémenter tout naturellement en faisant
appel uniquement à des portes NAND. On peut vérifier facilement que le
circuit suivant implémente la même fonction $$F = ((AB)^\prime \cdot  (CD)^\prime)^\prime = AB + CD$$

![img]({{site.baseurl}}/img/produit_sommeNAND2.svg "Produit de sommes NAND") 

Cette configuration s'interprète plus facilement en représentant la
porte de sortie comme une porte NOR avec les entrées complémentées
(version équivalente de la porte NAND). En effet, la complémentation
de chaque sortie de somme est compensée par la complémentation à
l'entrée de la porte de sortie.

![img]({{site.baseurl}}/img/produit_sommeNAND.svg "Produit de sommes NAND plus évidente")

