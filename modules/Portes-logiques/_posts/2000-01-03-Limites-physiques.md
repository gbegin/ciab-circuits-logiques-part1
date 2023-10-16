---
title: Limites physiques
---

# Limites physiques

Les portes logiques qu'on utilisera en pratique sont des dispositifs
électroniques dont le fonctionnement correspond, dans les grandes
lignes, aux comportements idéalisés des modèles abstraits de l'algèbre
de Boole. Mais il faut toujours garder à l'esprit que la
correspondance entre modèle et réalité physique n'est jamais
parfaite. En raffinant nos modèles pour y incorporer des
caractéristiques, limites ou contraintes appropriées, il sera possible
de mieux tenir compte de la réalité physique.

### Sortance ( *Fan-out*)

La sortance (*fan-out*) d'une porte logique mesure sa capacité à commander
d'autres portes reliées à sa sortie. Puisque les portes sont des
dispositifs électroniques qui doivent faire circuler un certain
courant électrique pour concrétiser les niveaux de tensions qui
définissent leurs valeurs d'entrée et de sortie, il y a une limite
pratique à la capacité d'une porte de fournir le courant nécessaire
pour faire réagir la sortie des portes qu'elle devrait commander. La sortance mesure cette limite, en nombre de portes à commander. Si on
connecte plus d'entrées à une sortie que sa valeur de sortance, cette
sortie ne pourra pas atteindre le niveau de tension adéquat, et les
opérations logiques seront faussées.

##  Modèles de délai

Dans la mesure où on respecte ses contraintes d'utilisation, notamment
de sortance, une porte logique se comporte globalement de la façon
attendue, étant donné sa fonction et les conventions de niveaux de
signal établies. Par exemple, le niveau signal à la sortie d'un
inverseur correspondra au niveau de signal attendu pour le complément
de la valeur logique à son entrée. Mais il faut garder à l'esprit que
les portes sont des dispositifs électroniques, et donc physiques,
sujets à des «imperfections» qui diffèrent du comportement idéalisé.

Une de ces «imperfections» dont on doit impérativement tenir compte
est le **délai de propagation** qui se manifeste comme un retard entre
le moment où le signal à l'entrée de la porte assume (se stabilise à)
son niveau de signal et le moment où la sortie de la porte atteint
son niveau de signal attendu. C'est en quelque sorte le délai entre
une action à l'entrée et son effet sur la sortie. Ce délai limite la
vitesse à laquelle on peut utiliser notre circuit logique. Si on
essaie d'effectuer des transitions plus rapides que le délai, le
comportement ne sera plus conforme aux attentes de conception. On doit
donc respecter une vitesse de commutation maximale imposée par les
délais de propagation.

Le délai de propagation peut dépendre de plusieurs facteurs: la
famille logique, le type de porte, le sens de la transition, la
sortance effective, les caractéristiques d'interconnexions, etc. Pour
faciliter l'analyse, on fait appel à des modèles de délais plus ou
moins sophistiqués. Un modèle très simple consiste à supposer un délai
de propagation moyen, constant pour toutes les portes d'une famille
donnée. Un modèle un peu plus subtil pourrait prendre en compte des
délais de propagation moyens différents par types de portes. Le délai
de propagation moyen est une caractéristique clé qui différencie les
différentes familles logiques. Les délais sont typiquement de l'ordre
de nanosecondes, permettant des vitesses de commutation dans les
dizaines, centaines, voire des milliers de MHz.

Lorsqu'un signal doit se propager à travers plusieurs portes, les
délais de propagation s'accumulent, limitant encore davantage la
vitesse de commutation de l'ensemble du circuit. La vitesse qui pourra
être atteinte pour l'ensemble d'un circuit sera typiquement déterminée
par le plus lent chemin (c'est-à-dire celui qui cumule le plus long temps de propagation).


### Modèles simples

À titre d'exemple, considérons une porte ET à deux entrées $$S = A B$$.
Le modèle le plus simple suppose une porte idéale, sans aucun délai:
le chronogramme suivant montre la sortie qui commute immédiatement
lorsque les conditions d'entrée changent.

![Porte ET sans délai.]({{site.baseurl}}/img/chronopasdelais.svg "Porte ET sans délai")
*Porte ET sans délai*

#### Modèle avec délai en sortie

Le modèle avec délai en sortie consiste à considérer un délai
fixe, qui affecte la sortie de la porte: la commutation prend
effet en sortie après un délai $$t_p$$.

![Porte ET avec délai en sortie.]({{site.baseurl}}/img/chrononodelaisortie.svg "Porte ET avec délai en sortie")
*Porte ET avec délai en sortie*

#### Modèle avec délai en entrée

Le modèle avec délai en entrée est plus nuancé, car il permet de
spécifier un délai différent selon l'entrée qui entraîne le
changement à la sortie.

![Porte ET avec délai aux entrées.]({{site.baseurl}}/img/chrononodelaientree.svg "Porte ET avec délai aux entrées")
*Porte ET avec délai aux entrées*

#### Modèle combiné

Le modèle combiné consiste à considérer des délais différents par
entrée et, en plus, un délai global en sortie.

### Condition de course et aléas

Un autre effet néfaste potentiel des délais à considérer est ce qu'on
appelle une **condition de course**. Considérons le circuit de la
figure suivante.  La sortie de la porte est $$s = a \cdot a^\prime$$
qui devrait normalement donner systématiquement 0. Mais le chemin
menant de l'entrée $$a$$ à l'entrée du haut de la porte ET est plus
court (en termes de délais) que le chemin qui mène à l'entrée du
bas. En effet, le signal $$a^\prime$$ est retardé d'un délai de
propagation $$t_{p1}$$ par rapport à $$a$$.

![Cas à risque de condition de course.]({{site.baseurl}}/img/course.svg "Cas à risque de condition de course")
*Cas à risque de condition de course*

En pratique, on pourrait observer un chronogramme qui s'apparente à
celui de la figure suivante, où on voit
que les deux signaux à l'entrée de la porte ET sont simultanément
égaux à 1 pendant une courte période. Une courte impulsion 1 sera donc
générée sur le signal $$s$$ en sortie de la porte ET, après le délai
de propagation $$t_{p2}$$ de celle-ci. Cette impulsion, qui ne
correspond à rien selon la logique du circuit est appelée un **aléa** (ou
en anglais, *glitch*).

![Chronogramme de la condition de course.]({{site.baseurl}}/img/chronocourse.svg "Chronogramme de la condition de course")
*Chronogramme de la condition de course*

Ces aléas peuvent être la source de problèmes et de dysfonctionnements
qui sont parfois difficiles à diagnostiquer, et il faut vraiment s'en
méfier. Une telle impulsion, quasi imperceptible, pourrait par exemple
déclencher le basculement de la valeur d'une cellule mémoire plus loin
dans le circuit.

## Porte tampon

La valeur binaire à la sortie d'une porte tampon est la même qu'à
l'entrée. La porte n'agit pas sur la valeur logique mais permet de
reconditionner le signal à son entrée pour le rendre, en sortie,
davantage conforme aux niveaux électriques de référence. Une porte
tampon est essentiellement utilisée pour renforcer et stabiliser le
niveau du signal. Une façon pratique de réaliser une porte tampon est
de placer deux inverseurs l'un à la suite de l'autre. L'utilisation de
portes tampons est un des moyens de s'assurer de respecter les
conditions de sortance.
