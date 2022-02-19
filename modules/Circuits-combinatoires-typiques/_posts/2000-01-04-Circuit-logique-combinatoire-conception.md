---
title: Circuit-logique-combinatoire-conception
---
## Conception d'un circuit combinatoire

Concevoir un circuit logique commence avec la formulation de la ou des
fonctions du système et se termine avec une implémentation en portes
logiques des fonctions logiques correspondantes. Voici les étapes à
suivre.

1.  À partir de l'expression du besoin ou des spécifications du
    système, déterminer combien d'entrées et de sorties sont
    requises, et leur assigner des noms de variables. Le choix des noms
    devrait faciliter leur interprétation en lien avec leur fonction.

2.  Formuler le tableau de vérité qui décrit les valeurs logiques que
    doivent assumer les sorties en fonction des différentes
    combinaisons d'entrées.

3.  Simplifier les expressions logiques pour les différentes fonctions,
    en tenant éventuellement compte des partages possibles d'éléments
    intermédiaires.

4.  Tracer le circuit logique résultant, et le valider (à la main ou
    mieux, par simulation).

L'étape 2 est cruciale, car ce qui sera implémenté (s'il n'y a pas
d'erreurs) est exactement ce que le tableau de vérité spécifie. On
doit donc s'assurer que le tableau est correctement rempli et
représente véritablement les besoins identifiés. Si des hypothèses ou
des choix doivent être faits, notamment dans le cas où l'expression
informelle des besoins est incomplète ou ambiguë, ces choix doivent
être clairement identifiés et documentés, permettant le cas échéant de
les modifier lorsque le système est mis à l'épreuve en fonctionnement.

N'importe quelle méthode de simplification peut être utilisée pour
l'étape 3, mais il faut aussi prendre en compte le types de portes
disponibles pour l'implémentation, les délais de propagations à
travers les portes, le nombre d'interconnexions entre sorties et
entrées de portes, et tout autre facteur pratique susceptible
d'orienter les décisions finales.


## Alternatives d'implémentation

Considérons la fonction logique correspondant au diag-K suivant. 

![img]({{site.baseurl}}/img/kmap3altern.svg "Fonction combinatoire $$Y$$ à réaliser") 
*Fonction combinatoire $$Y$$ à réaliser*

### Implémentations via la fonction directe

1.  Implémentation en *somme de produits*

    En *somme de produits*, on a $$Y = bc + a^\prime b + a b^\prime
    c^\prime $$ pour la fonction et $$Y^\prime = a^\prime b^\prime +
    b^\prime c + a b c^\prime $$ pour son complément. Les
    implémentations possibles pour la fonction directe sont illustrées
    ci-dessous.
    
    ![img]({{site.baseurl}}/img/circ_altern_1.svg "Implémentation de $$Y$$ en *somme de produits*")
	*Implémentation de $$Y$$ en S de P*
    
    ![img]({{site.baseurl}}/img/circ_altern_2.svg "Implémentation (en NAND) de $$Y$$ en *somme de produits*")
	*Implémentation (en NAND) de $$Y$$ en S de P*

2.  Implémentation en *produit de sommes*

    En *produit de sommes*, on a $$Y =(a + b ) (b + c^\prime ) (a^\prime +
    ba^\prime + c)$$ pour la fonction et $$Y^\prime = (b^\prime +c^\prime
    )(a+b^\prime )(a^\prime +b+c)$$ pour son complément. Les
    implémentations possibles pour la fonction directe sont illustrées
    ci-dessous.
    
    ![img]({{site.baseurl}}/img/circ_altern_ps1.svg "Implémentation de $$Y$$ en *produit de sommes*")
	*Implémentation de $$Y$$ en P de S*
    
    ![img]({{site.baseurl}}/img/circ_altern_ps2.svg "Implémentation (en NOR) de $$Y$$ en *produit de sommes*")
	*Implémentation (en NOR) de $$Y$$ en P de S*


### Implémentations via la fonction complémentaire

On peut aussi implémenter la fonction à partir de la fonction
complémentaire $$Y^\prime$$, en se basant sur le complément $$Y^\prime
= (b^\prime +c^\prime )(a+b^\prime )(a^\prime +b+c)$$ et en inversant
la sortie. Voici les implémentations que l'on obtient alors.

1.  Implémentation en *somme de produits*

    ![img]({{site.baseurl}}/img/circ_altern_comp_sp1.svg "Implémentation via $$Y^\prime$$ en *somme de produits*")
	*Implémentation via $$Y^\prime$$ en S de P*
    
    ![img]({{site.baseurl}}/img/circ_altern_comp_sp2.svg "Implémentation via $$Y^\prime$$ en *somme de produits*")
	*Implémentation via $$Y^\prime$$ en S de P, autre forme*

2.  Implémentation en *produit de sommes*

    En *produit de sommes*, en se basant sur le complément $$Y^\prime =
    (b^\prime +c^\prime )(a+b^\prime )(a^\prime +b+c)$$.
    
    ![img]({{site.baseurl}}/img/circ_altern_comp_ps1.svg "Implémentation via $$Y^\prime$$ en *produit de sommes*") 
	*Implémentation via $$Y^\prime$$ en P de S*
    
    ![img]({{site.baseurl}}/img/circ_altern_comp_ps2.svg "Implémentation via $$Y^\prime$$ en *produit de sommes*") 
*Implémentation via $$Y^\prime$$ en P de S, autre forme*
