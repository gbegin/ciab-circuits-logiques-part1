---
title: Tableau d'implication
---

### Tableau d'implication


La méthode du tableau d'implication facilite l'identification des
états redondants à éliminer. Considérons le tableau d'état suivant,
qui correspond cette fois-ci à une machine de Moore dont nous allons
réduire le nombre d'états.

<table id="org32dbd72" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 4 :</span> Tableau d'état (machine de Moore)</caption>

<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">État présent</th>
<th scope="col" class="org-left">État suivant</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-left">État suivant</th>
<th scope="col" class="org-right">$$S$$</th>
</tr>


<tr>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-left">$$x=0$$</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-left">$$x=1$$</th>
<th scope="col" class="org-right">&#xa0;</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">a</td>
<td class="org-left">g</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">c</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">b</td>
<td class="org-left">f</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">h</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">c</td>
<td class="org-left">e</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">d</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">d</td>
<td class="org-left">a</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">c</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">e</td>
<td class="org-left">c</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">a</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">f</td>
<td class="org-left">f</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">b</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">g</td>
<td class="org-left">a</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">c</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">h</td>
<td class="org-left">c</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">g</td>
<td class="org-right">1</td>
</tr>
</tbody>
</table>

Un tableau d'implication comporte une entrée pour chaque paire d'états
dans le tableau d'état. Avec $$n$$ états initialement (ici on a
$$n=8$$), on étiquettera les colonnes avec les $$n-1$$ premiers états,
et les lignes avec les $$n-1$$ derniers états. La première case vide,
en haut à gauche, sera notée [a;b] et la dernière en bas à droite sera
[g;h]. Voici le tableau avant d'être rempli. Seules les cases qui ne
comportent pas de \_ peuvent être remplies. Il n'y a par exemple rien
d'utile à mettre dans une case étiquetée [b;b].

| b | &nbsp; &nbsp; | &nbsp; \_ | &nbsp;  \_ | &nbsp;  \_ | &nbsp;  \_ | &nbsp; \_ | &nbsp;  \_ |
| c |               |           | \_         | \_         | \_         | \_        | \_         |
| d |               |           |            | \_         | \_         | \_        | \_         |
| e |               |           |            |            | \_         | \_        | \_         |
| f |               |           |            |            |            | \_        | \_         |
| g |               |           |            |            |            |           | \_         |
| h |               |           |            |            |            |           |            |
|---|---------------|-----------|------------|------------|------------|-----------|------------|
|   | a             | b         | c          | d          | e          | f         | g          |
{:.mbtablestyle}

1.  On applique la procédure en considérant chaque case du tableau, ce
    qui permet de comparer chaque paire de lignes du tableau d'état.
    -   On vérifie dans un premier temps si les sorties sont
        différentes. Si c'est le cas, on met un X dans la case. Par
        exemple ici, *a* et *c*, *a* et *e*, *a* et *f*, *a* et *h*
        ont des sorties différentes, donc on place des X dans les
        cases [a;c], [a;e], [a;f] et [a;h].
    -   Si les sorties sont les mêmes, on place dans la case les
        paires d'états qu'une équivalence nécessiterait. Par exemple
        pour la case [a;b], une équivalence entre *a* et *b*
        nécessiterait les équivalences g=f et c=h entre les états
        prochains. Pour la case [a;d], une équivalence entre *a* et
        *d* nécessiterait les équivalences g=a et c=c. Cette dernière,
        évidente, n'est pas inscrite dans le tableau. Pour [b;d], on
        trouve f=a et h=c.
    -   Si les sorties sont les mêmes et les paires d'états suivants sont
        identiques ou encore sont les états mêmes qu'on est en train de
        considérer, on met directement OUI dans le tableau. Par exemple,
        pour la case [a;g] on a les paires g=a et c=c, donc on met
        OUI. Pour la case [d;g], on a a=a et c=c, on met OUI
        également. On continue ainsi, de colonne en colonne, pour obtenir
        après ces étapes le résultat suivant.
    
    |---|:-----------------:|:--------:|:--------:|:-----------------:|:--------:|:--------:|:---------------:|
	| b | g=f c=h           | \_       | \_       | \_                | \_       | \_       | \_              |
	| c | &nbsp; X          | &nbsp; X | \_       | \_                | \_       | \_       | \_              |
	| d | g=a               | f=a h=c  | &nbsp; X | \_                | \_       | \_       | \_              |
	| e | &nbsp; X          | &nbsp; X | d=a      | &nbsp; X          | \_       | \_       | \_              |
	| f | &nbsp; X          | &nbsp; X | e=f d=b  | &nbsp; X          | c=f a=b  | \_       | \_              |
	| g | &nbsp; OUI &nbsp; | f=a h=c  | &nbsp; X | &nbsp; OUI &nbsp; | &nbsp; X | &nbsp; X | \_              |
	| h | &nbsp; X          | &nbsp; X | e=c d=g  | &nbsp; X          | a=g      | f=c b=g  | &nbsp; X &nbsp; |
	|---|:-----------------:|:--------:|:--------:|:-----------------:|:--------:|:--------:|:---------------:|
	|   | a                 | b        | c        | d                 | e        | f        | g               |
	{:.mbtablestyle}

2.  L'étape suivante consiste à considérer chaque case qui
    comporte une ou des paires d'états impliqués. On regarde la case
    correspondant à chaque paire, et s'il y a un X dans la case, alors
    l'implication ne fonctionne pas. Par exemple, la case [a;b] repose
    sur les équivalences g=f c=h. Or si on regarde la case [f;g], on
    voit qu'il s'y trouve un X, ce qui veut dire que *f et /g* ne peuvent
    pas être équivalents, ce qui implique que a et b ne pourront pas
    être équivalents. Ce n'est pas la peine de regarder la case [c;h].
    On remplacera donc les paires de la case [a;b] par un XX, pour
    faire ressortir ces nouveaux échecs.
3.  Un XX dans le tableau peut faire échouer d'autres implications. Il
    faut donc revoir les cases avec des paires d'états impliqués pour
    voir s'il faut changer leur statut. On continue à revoir ainsi
    jusqu'à ce qu'il n'y ait plus d'ajouts de XX. On obtient
    finalement le tableau suivant:

	|---|:----------------:|:----------------:|:----------------:|:----------------:|:----------------:|:----------------:|:----------------:|
	| b | &nbsp; XX &nbsp; | &nbsp; \_ &nbsp; | &nbsp; \_ &nbsp; | &nbsp; \_ &nbsp; | &nbsp; \_ &nbsp; | &nbsp; \_ &nbsp; | &nbsp; \_ &nbsp; |
	| c | X                | X                | \_               | \_               | \_               | \_               | \_               |
	| d | g=a              | XX               | X                | \_               | \_               | \_               | \_               |
	| e | X                | X                | d=a              | X                | \_               | \_               | \_               |
	| f | X                | X                | XX               | X                | XX               | \_               | \_               |
	| g | OUI              | XX               | X                | OUI              | X                | X                | \_               |
	| h | X                | X                | e=c d=g          | X                | a=g              | XX               | X                |
	|---|:----------------:|:----------------:|:----------------:|:----------------:|:----------------:|:----------------:|:----------------:|
	|   | a                | b                | c                | d                | e                | f                | g                |
	{:.mbtablestyle}

4.  Après cette étape, toutes les cases qui contiennent OUI ou des
    paires d'implications indiquent des équivalences d'états. Ici, on
    a les équivalences suivantes: a=d, a=g, c=e, c=h, d=g, e=h. Les
    états uniques résultants sont *a*, *b*, *c* et *f*. On obtient le
    tableau d'état réduit suivant:

<table id="orgbdca5b3" border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption class="t-above"><span class="table-number">Tableau 5 :</span> Tableau d'état réduit (machine de Moore)</caption>

<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">État présent</th>
<th scope="col" class="org-left">État suivant</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-left">État suivant</th>
<th scope="col" class="org-right">\(S\)</th>
</tr>


<tr>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-left">\(x=0\)</th>
<th scope="col" class="org-left">&#xa0;</th>
<th scope="col" class="org-left">\(x=1\)</th>
<th scope="col" class="org-right">&#xa0;</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">a</td>
<td class="org-left">a</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">c</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">b</td>
<td class="org-left">f</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">c</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-left">c</td>
<td class="org-left">c</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">a</td>
<td class="org-right">1</td>
</tr>


<tr>
<td class="org-left">f</td>
<td class="org-left">f</td>
<td class="org-left">&#xa0;</td>
<td class="org-left">b</td>
<td class="org-right">1</td>
</tr>
</tbody>
</table>

