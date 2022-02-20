---
title: Démarche d'analyse
---

# Démarche d'analyse

Analyser un circuit logique séquentiel a pour but de déterminer le
comportement qu'aura le circuit selon les séquences d'entrées qui lui
seront appliquées et l'état dans lequel il se trouve initialement. On
voudra aussi connaître quelles séquences de sorties seront produites.

Dans la mesure où un circuit comporte une ou des bascules (peu importe
le type) et un signal d'horloge, on peut considérer qu'il s'agit d'un
circuit séquentiel synchrone. Le type de bascule sera pris en compte
pour l'analyse, qui consistera à déterminer, pour un état présent
donné, quel seront les prochains états possibles selon les valeurs
d'entrée.

Les grandes lignes de la démarche sont les suivantes.

1.  Identification des éléments fonctionnels:
    1.  entrées externes
    
    2.  éléments de mémoire
    
    3.  décodeur de prochain état
    
    4.  sorties externes
    
    5.  décodeur de sortie
2.  Expressions logiques du décodeur de prochain état: établies pour
    chaque entrée des bascules, en fonction des entrées externes et des
    variables d'état.
3.  Expressions logiques des sorties externes, établies en fonction des
    entrées externes et des variables d'état.
4.  Construction du tableau d'excitation.
5.  Diagramme d'état.
6.  Interprétation du comportement du circuit séquentiel.

Au centre de l'analyse se trouve l'analyse des circuits combinatoires
qui déterminent ce que seront les entrées des bascules. Nous
chercherons à établir les **équations de transition** qui précisent ce
que sera le prochain état en fonction des entrées et de l'état
présent.
