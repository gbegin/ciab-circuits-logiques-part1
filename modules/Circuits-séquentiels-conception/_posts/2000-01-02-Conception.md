---
title: Conception d'un circuit séquentiel synchrone
---


# Conception d'un circuit séquentiel synchrone

Concevoir un circuit logique séquentiel permet de répondre à un besoin
pratique qui ne peut pas être satisfait par un circuit combinatoire.
Le point de départ est une description, la plus précise possible, du
besoin à remplir: quelle doit ou doivent être les entrées, les
sorties, les conditions qui font passer d'un état au suivant,
etc. Pour un besoin donné, une multitude de solutions,
fonctionnellement équivalentes sont possibles, aussi il faudra établir
des critères ou identifier des contraintes qui permettront d'orienter
la conception et le choix final d'une solution. Deux systèmes peuvent
avoir un même comportement vu de l'extérieur, mais comporter des
nombres d'états internes différents.

Des considérations pratiques nous amèneront souvent à vouloir réduire
le nombre d'états nécessaires, et à simplifier les différents circuit
combinatoires utilisés.


## Spécification fonctionnelle

Comme dans tout problème de conception, la formulation en mots de la
spécification du système est cruciale. Appliquer parfaitement une
procédure de conception en se basant sur une spécification erronée ne
peut pas conduire à système adéquat.

Il faudra un bon bagage d'expérience et d'intuition au concepteur pour
pouvoir interpréter et traduire correctement une description
informelle, plus souvent qu'autrement incomplète, ambiguë et
imprécise, en un design concret qui répond au besoin maladroitement
exprimé. Il revient au concepteur de s'assurer que ce qu'il a compris
correspond bien à ce qui était demandé.

La première question à poser est: Que doit faire le système? Suivront
d'autres questions, amenant à définir davantage de détails: Combien
d'entrées sont nécessaires? Doit-il y avoir des entrées? Combien de
sorties sont nécessaires?. Le comportement du système pourra être
essentiellement caractérisé en répondant à la question: Quelle doit
être la séquence des sorties, pour une certaine séquence d'entrées?
Mais comme les séquences d'entrées peuvent être en nombre infini, il
faudra identifier des patrons qui permettront de résumer le
comportement du système.
