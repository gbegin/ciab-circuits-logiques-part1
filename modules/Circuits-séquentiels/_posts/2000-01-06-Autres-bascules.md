---
title: Autres bascules
---

### Autres bascules

Il y a essentiellement trois opérations possibles pour une bascule:
mettre sa sortie à 1 (*set*), mettre sa sortie à 0 (*reste*) ou faire
basculer son état de sortie (*toggle*).


### Bascule JK

Une bascule JK comporte deux entrées, ce qui permet de lui faire
exécuter les trois opérations. Activer seulement l'entrée $$J$$ fait
un *set*, activer seulement l'entrée $$K$$ fait un *reset* et activer
les deux entrées fait un *toggle*. On peut réaliser une bascule JK
comme sur la figure suivante.

![img]({{site.baseurl}}/img/bascule_JK.svg "Bascule JK")
*Bascule JK*

La figure qui suit montre le chronogramme de fonctionnement d'une
bascule JK. La bascule fait d'abord un *set*, puis un *reset* et enfin
trois *toggles* de suite.

![img]({{site.baseurl}}/img/chron_JK.svg "Chronogramme de la bascule JK")
*Chronogramme de la bascule JK*


### Bascule T

La bascule T (T pour *toggle*) change d'état à chaque déclenchement
lorsque l'entrée $$T$$ est activée. On peut la réaliser à partir d'une
bascule D ou d'une bascule JK, comme on peut le voir sur la figure suivante.

![img]({{site.baseurl}}/img/basculeT.svg "Bascule T")
*Bascule T*

