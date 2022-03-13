---
title: Lecture et écriture
---

### Lecture et écriture

L'opération choisie, écriture ou lecture, est commandée par un ou des entrées à cet effet. L'accès à un espace-mémoire (un mot) se fait selon une séquence bien précise. Pour une écriture:

1.  Les bits d'adresse du mot sont appliqués aux lignes d'adresses.
2.  Les données à écrire sont appliquées aux lignes d'entrée.
3.  On active l'entrée *Écriture*.

Les données de l'entrée sont stockées dans la case-mémoire adressée.

Pour une lecture:

1.  Les bits d'adresse du mot sont appliqués aux lignes d'adresses.
2.  On active l'entrée *Lecture*.

Les données présentes dans la case-mémoire adressée sont disponibles à
la sortie de la mémoire.

Les mémoires disponibles sur le marché opte souvent pour une
combinaison de signaux de contrôle, avec un seul signal qui détermine
le sens de l'action, comme on peut le voir dans le tableau
[1](#org472ff24). Le signal *Enable*, parfois appelé *Chip
select*, permet d'activer une mémoire dans un ensemble où plusieurs
mémoires sont utilisées.

<table id="org472ff24" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 1 :</span> Signaux de contrôle d'une mémoire</caption>

<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-right"><i>Enable</i></th>
<th scope="col" class="org-right"><i>Lecture/écriture</i></th>
<th scope="col" class="org-left">Action</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-right">X</td>
<td class="org-left">Aucune</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">0</td>
<td class="org-left">Écriture</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-right">1</td>
<td class="org-left">Lecture</td>
</tr>
</tbody>
</table>


### Bus de données

Pour acheminer les données lues ou à écrire dans la mémoire, on
utilise des tampons émetteur-récepteurs de bus (voir section [Portes à trois états et tampon de bus]({{site.baseurl}}{% post_url modules/Circuits-combinatoires-typiques/2000-01-12-Démultiplexeur %}), organisés en vecteur, pour créer un
**bus de données** qui permet un aller-retour des données, selon le sens
de l'action. Un signal dérivé du signal *Lecture/écriture* et *Chip
select (CS)* est typiquement utilisé pour commander l'entrée de
contrôle, comme on le voit sur la figure suivante.

 

![img]({{site.baseurl}}/img/bus_trans8.svg "Bus de données, 8 bits")
*Bus de données, 8 bits*
