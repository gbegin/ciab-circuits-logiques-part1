---
title: Modèle d'un circuit séquentiel
---

## Modèle d'un circuit séquentiel

Les circuits logiques séquentiels sont ceux qui comportent de la
mémoire. Le modèle général d'un circuit séquentiel est illustré sur la
figure [491](#orgf171663). On y voit qu'il y a une boucle de rétroaction, qui
fait que les valeurs binaires stockées dans les éléments de mémoire
contribuent au calcul des sorties. Les sorties du circuit à un instant
donné ne dépendent donc pas seulement des entrées présentes à ce
moment, mais aussi de ces valeurs qui sont mémorisées dans le
système. Pour décrire cette situation dans laquelle se trouvent les
valeurs stockées en mémoire, on parle de l'**état** du système. Selon
les entrées et l'état à un instant donné, le système pourra changer
d'état selon les changements qui seront apportés aux valeurs
mémorisées par la portion combinatoire.

On verra donc le système évoluer au fil du temps, passant d'un état à
un autre, et générant des sorties en fonction des entrées et de l'état
du moment. Intuitivement, on peut penser que le nombre d'états
distincts sera fonction du nombre de valeurs binaires qui seront
mémorisées. Le comportement d'un système séquentiel est donc
caractérisé par une séquence temporelle d'entrées, de sorties et de
valeurs interne d'état.

![img]({{site.baseurl}}/img/circuit_seq.png "Modèle de circuit séquentiel")
*Modèle de circuit séquentiel*

On peut distinguer les circuits séquentiels selon la relation de
synchronisation qui existe entre les différents signaux du
système. Dans un circuit séquentiel **synchrone**, le comportement du
système peut se définir en fonction des valeurs de ses signaux à des
instants discrets prédéterminés. Le comportement d'un circuit
séquentiel **asynchrone** dépend à tout moment des signaux d'entrée et
de l'ordre dans lequel ces signaux changent.

Un circuit séquentiel synchrone fait appel à un signal spécial appelé
**horloge** qui rythme les changement d'état et de sorties afin qu'il se
produisent à des instants discrets. Les éléments de mémoire qui
stockent les valeurs binaires sont appelés **bascules** (*flip-flops* en
anglais). Il existe différents types de bascules. Nous les étudierons
en détail, car elles sont à la base des circuits séquentiels les plus
utilisés. La figure [494](#org63e635a) présente le modèle général d'un
circuit séquentiel synchrone.

![img]({{site.baseurl}}/img/circuit_seq_sync.png "Modèle de circuit séquentiel synchrone")
*Modèle de circuit séquentiel synchrone"*

Le signal d'horloge est typiquement une onde carrée, telle
qu'illustré sur la figure [496](#org74a3f11).

![img]({{site.baseurl}}/img/horloge.svg "Signal d'horloge")
*Signal d'horloge*


## Éléments de mémoire

Un élément de mémoire peut maintenir son état binaire indéfiniment (à
condition, évidemment, qu'il soit alimenté). Son état est observable
par l'intermédiaire de ses sorties. On doit agir via la ou les entrées
de l'élément pour le faire changer d'état. Les différents types
d'éléments de mémoire sont caractérisés par le nombre et le type
d'entrées.

Les éléments de mémoire qui sont contrôlés par les niveaux de leurs
entrées sont appelés des **loquets** (*latches* en anglais). Les
éléments contrôlés par des changements ou **transitions** de niveaux
sont appelés des bascules. Les transitions sont appliquées à une
entrée spéciale d'horloge qui sert à déclencher les changements d'état
à des instants précis. Les loquets sont des ingrédients de base dans
la conception des bascules. Nous les étudierons en premier.



