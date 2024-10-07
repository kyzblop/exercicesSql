### Exercices SQL
Il s'agit d'une suite d'exercices sur une base SQL afin de pratiquer les requêtes SQL.

Prérequis : Créer une base de données (ici : "lpecom_bdd"), importer les données et l'utiliser (requête : use lpecom_bdd;)

<details>
  <summary>
    Partie 1
  </summary>
  
## Exercice 1
_Quelle requête utiliser pour afficher l'ensemble des enregistrements de la table lpecom_livres ?_

- Requêtes à saisir :

```
select * from lpecom_livres;
```

- Resultat :

| id_livre | titre                        | isbn_10    | auteur                  | prix |
|----------|------------------------------|------------|-------------------------|------|
|        1 | Forteresse digitale          | 2709626306 | Dan Brown               | 20.5 |
|        2 | La jeune fille et la nuit     | 2253237620 | Guillaume Musso         | 21.9 |
|        3 | T'choupi se brosse les dents | 2092589547 | Thierry Courtin         |  5.7 |
|        4 | La Dernière Chasse           | 2226439412 | Jean-Christophe Grangé  | 22.9 |
|        5 | Le Signal                    | 2226319484 | Maxime Chattam          | 23.9 |

<br>



## Exercice 2
_Quelle requête utiliser pour sélectionner uniquement les livres qui ont un prix strictement supérieur à
20 dans la table lpecom_livres ?_

- Requêtes à saisir :
```
select * from lpecom_livres
where prix > 20;
```

- Resultat :

| id_livre | titre                      | isbn_10    | auteur                  | prix |
|----------|----------------------------|------------|-------------------------|------|
|        1 | Forteresse digitale        | 2709626306 | Dan Brown               | 20.5 |
|        2 | La jeune fille et la nuit   | 2253237620 | Guillaume Musso         | 21.9 |
|        4 | La Dernière Chasse         | 2226439412 | Jean-Christophe Grangé  | 22.9 |
|        5 | Le Signal                  | 2226319484 | Maxime Chattam          | 23.9 |


<br>

## Exercice 3
_Quelle requête utiliser pour trier les enregistrements de la table lpecom_livres du prix le plus élevé
au prix le plus bas ?_

- Requête à saisir :
```
select * from lpecom_livres
order by prix desc;
```

- Resultat :

| id_livre | titre                        | isbn_10    | auteur                  | prix |
|----------|------------------------------|------------|-------------------------|------|
|        5 | Le Signal                    | 2226319484 | Maxime Chattam          | 23.9 |
|        4 | La Dernière Chasse           | 2226439412 | Jean-Christophe Grangé  | 22.9 |
|        2 | La jeune fille et la nuit     | 2253237620 | Guillaume Musso         | 21.9 |
|        1 | Forteresse digitale          | 2709626306 | Dan Brown               | 20.5 |
|        3 | T'choupi se brosse les dents | 2092589547 | Thierry Courtin         |  5.7 |

<br>

## Exercice 4
_Quelle requête utiliser pour récupérer le prix du livre le plus élevé de la table lpecom_livres ?_

- Requête à saisir :
```
select max(prix) from lpecom_livres;
```

- Resultat :

| max(prix) |
|-----------|
|      23.9 |

<br>

## Exercice 5
_Quelle requête utiliser pour récupérer les livres de la table lpecom_livres qui ont un prix compris
entre 20 et 22 ?_

- Requête à saisir :
```
select * from lpecom_livres
where prix between 20 and 22;
```

- Resultat :

| id_livre | titre                      | isbn_10    | auteur          | prix |
|----------|----------------------------|------------|-----------------|------|
|        1 | Forteresse digitale        | 2709626306 | Dan Brown       | 20.5 |
|        2 | La jeune fille et la nuit   | 2253237620 | Guillaume Musso | 21.9 |


<br>

## Exercice 6
_Quelle requête utiliser pour récupérer tous les livres de la table lpecom_livres à l'exception de celui
portant la valeur pour la colonne isbn_10 : 2092589547 ?_

- Requête à saisir :
```
select * from lpecom_livres
where not isbn_10 = 2092589547;
```

- Resultat :

| id_livre | titre                      | isbn_10    | auteur                  | prix |
|----------|----------------------------|------------|-------------------------|------|
|        1 | Forteresse digitale        | 2709626306 | Dan Brown               | 20.5 |
|        2 | La jeune fille et la nuit   | 2253237620 | Guillaume Musso         | 21.9 |
|        4 | La Dernière Chasse         | 2226439412 | Jean-Christophe Grangé  | 22.9 |
|        5 | Le Signal                  | 2226319484 | Maxime Chattam          | 23.9 |

<br>

## Exercice 7
_Quelle requête utiliser pour récupérer le prix du livre le moins élevé de la table lpecom_livres en
renommant la colonne dans les résultats par minus ?_

- Requête à saisir :
```
select min(prix) as minus from lpecom_livres;
```

- Resultat :

| minus |
|-------|
|   5.7 |

<br>

## Exercice 8
_Quelle requête utiliser pour sélectionner uniquement les 3 premiers résultats sans le tout premier de
la table lpecom_livres ?_

- Requête à saisir :
```
select * from lpecom_livres limit 3 offset 1;
```

- Resultat :

| id_livre | titre                        | isbn_10    | auteur                  | prix |
|----------|------------------------------|------------|-------------------------|------|
|        2 | La jeune fille et la nuit     | 2253237620 | Guillaume Musso         | 21.9 |
|        3 | T'choupi se brosse les dents | 2092589547 | Thierry Courtin         |  5.7 |
|        4 | La Dernière Chasse           | 2226439412 | Jean-Christophe Grangé  | 22.9 |

<br>
</details>

<details>
<summary>
  Partie 2
</summary>

## Exercice 1
_Quelle requête utiliser pour afficher l'id des étudiants qui ont participé à au moins un examen ?_

- Requête à saisir :
```
select distinct id_etudiant from lpecom_examens;
```

- Resultat :

| id_etudiant |
|-------------|
|          30 |
|          33 |
|          34 |
|          31 |
|          32 |
|          36 |

<br>

## Exercice 2
_Quelle requête utiliser pour compter le nombre d'étudiants qui ont participé à au moins un examen ?_

- Requête à saisir :
```
select count(distinct id_etudiant) from lpecom_examens;
```

- Resultat :

| count(distinct id_etudiant) |
|-----------------------------|
|                           6 |

<br>

## Exercice 3
_Quelle requête utiliser pour calculer la moyenne de l'examen portant l'id : 45 ?_

- Requête à saisir :
```
select avg(note) from lpecom_examens
where id_examen = 45;
```

- Resultat :

| avg(note) |
|-----------|
|     12.25 |

<br>

## Exercice 4
_Quelle requête utiliser pour récupérer la meilleure note de l'examen portant l'id : 87 ?_

- Requête à saisir :
```
select max(note) from lpecom_examens
where id_examen = 87;
```

- Resultat :

| max(note) |
|-----------|
|        14 |

<br>

## Exercice 5
_Quelle requête utiliser pour afficher l'id des étudiants qui ont eu plus de 11 à l'examen 45 ou plus de
12 à l'examen 87 ?_

- Requête à saisir :
```
select id_etudiant from lpecom_examens
where id_examen = 45 and note > 11
or (id_examen = 87 and note > 12);
```

- Resultat :

| id_etudiant |
|-------------|
|          33 |
|          31 |
|          31 |
|          36 |
|          34 |

<br>

## Exercice 6
_Quelle requête utiliser pour afficher tous les enregistrements de la table lpecom_examens avec en
plus, si c'est possible, le prénom et le nom de l'étudiant ?_

- Requête à saisir :
```
select lpecom_examens.id, lpecom_examens.id_examen, lpecom_examens.id_etudiant, lpecom_examens.matiere, lpecom_examens.note,
lpecom_etudiants.prenom, lpecom_etudiants.nom from lpecom_examens
left join lpecom_etudiants on lpecom_examens.id_etudiant = lpecom_etudiants.id_etudiant;
```

- Resultat :

| id  | id_examen | id_etudiant | matiere             | note | prenom   | nom      |
|-----|-----------|-------------|---------------------|------|----------|----------|
| 788 |        45 |          30 | Histoire-Geographie | 10.5 | Joseph   | Biblo    |
| 789 |        87 |          33 | Mathématiques       |   14 | Ted      | Bundy    |
| 790 |        87 |          34 | Mathématiques       |    4 | Caroline | Martinez |
| 791 |        45 |          31 | Histoire-Geographie | 15.5 | Paul     | Bismuth  |
| 792 |        45 |          32 | Histoire-Geographie |    8 | Jean     | Michel   |
| 793 |        87 |          31 | Mathématiques       |   14 | Paul     | Bismuth  |
| 794 |        45 |          33 | Histoire-Geographie |  9.5 | Ted      | Bundy    |
| 795 |        45 |          36 | Histoire-Geographie |   13 | NULL     | NULL     |
| 796 |        45 |          34 | Histoire-Geographie |   17 | Caroline | Martinez |
| 797 |        87 |          30 | Mathématiques       |  7.5 | Joseph   | Biblo    |


<br>

## Exercice 7
_Quelle requête utiliser pour afficher les enregistrements de la table lpecom_examens avec le
prénom et le nom de l'étudiant, uniquement quand les étudiants sont présents dans la table
lpecom_etudiants ?_

- Requête à saisir :

```
select lpecom_examens.id, lpecom_examens.id_examen, lpecom_examens.id_etudiant, lpecom_examens.matiere, lpecom_examens.note,
lpecom_etudiants.prenom, lpecom_etudiants.nom from lpecom_examens
inner join lpecom_etudiants on lpecom_examens.id_etudiant = lpecom_etudiants.id_etudiant;
```

- Resultat :


| id  | id_examen | id_etudiant | matiere             | note | prenom   | nom      |
|-----|-----------|-------------|---------------------|------|----------|----------|
| 788 |        45 |          30 | Histoire-Geographie | 10.5 | Joseph   | Biblo    |
| 789 |        87 |          33 | Mathématiques       |   14 | Ted      | Bundy    |
| 790 |        87 |          34 | Mathématiques       |    4 | Caroline | Martinez |
| 791 |        45 |          31 | Histoire-Geographie | 15.5 | Paul     | Bismuth  |
| 792 |        45 |          32 | Histoire-Geographie |    8 | Jean     | Michel   |
| 793 |        87 |          31 | Mathématiques       |   14 | Paul     | Bismuth  |
| 794 |        45 |          33 | Histoire-Geographie |  9.5 | Ted      | Bundy    |
| 796 |        45 |          34 | Histoire-Geographie |   17 | Caroline | Martinez |
| 797 |        87 |          30 | Mathématiques       |  7.5 | Joseph   | Biblo    |

<br>

## Exercice 8
_Quelle requête utiliser pour afficher uniquement le nom et le prénom de l'étudiant avec l'id : 30 avec
la moyenne de ses deux examens dans une colonne moyenne ?_

- Requête à saisir :
```
select lpecom_etudiants.nom, lpecom_etudiants.prenom, avg(lpecom_examens.note) as moyenne from lpecom_etudiants
inner join lpecom_examens on lpecom_etudiants.id_etudiant = lpecom_examens.id_etudiant
where lpecom_etudiants.id_etudiant = 30;
```

- Resultat :

| nom   | prenom | moyenne |
|-------|--------|---------|
| Biblo | Joseph |       9 |

<br>

## Exercice 9
_Quelle requête utiliser pour afficher les 3 meilleurs examens, du meilleur au moins bon, avec le
prénom et le nom de l'étudiant associé ?_

- Requête à saisir :
```
select lpecom_examens.id, lpecom_examens.id_examen, lpecom_examens.id_etudiant, lpecom_examens.matiere, lpecom_examens.note,
lpecom_etudiants.prenom, lpecom_etudiants.nom from lpecom_examens
inner join lpecom_etudiants on lpecom_examens.id_etudiant = lpecom_etudiants.id_etudiant
order by lpecom_examens.note desc
limit 3;
```

- Resultat :

| id  | id_examen | id_etudiant | matiere             | note | prenom   | nom      |
|-----|-----------|-------------|---------------------|------|----------|----------|
| 796 |        45 |          34 | Histoire-Geographie |   17 | Caroline | Martinez |
| 791 |        45 |          31 | Histoire-Geographie | 15.5 | Paul     | Bismuth  |
| 793 |        87 |          31 | Mathématiques       |   14 | Paul     | Bismuth  |

<br>
</details>

<details>
  <summary>
  Partie 3
  </summary>
  


## Exercice 1
_Quel est le résultat de la requête ci-dessous ?_

```
SELECT id, prenom, nom
FROM lpecom_realisateurs
WHERE nation = "us"
AND sexe = 1;
```

Cette requête affiche l'id, le prénom et le nom des réalisatrices originaires des US.

- Resultat :

| id | prenom | nom     |
|----|--------|---------|
| 47 | Patty  | Jenkins |

<br>

## Exercice 2
_Quel est le résultat de la requête ci-dessous ?_

```
SELECT *
FROM lpecom_realisateurs
WHERE sexe = "0"
ORDER BY nom DESC
LIMIT 1;
```

Cette requête affiche toutes les données des réalisateurs masculins rangés par ordre anti-alphabetique en ne prenant que la première valeur (soit le premier nom dans l'ordre anti-alphabetique)

- Resultat :


| id | nom   | prenom | sexe | nation |
|----|-------|--------|------|--------|
| 16 | Scott | Ridley |    0 | uk     |

<br>

## Exercice 3
_Quel est le résultat de la requête ci-dessous ?_

```
SELECT f.id, f.nom AS film, r.prenom, r.nom
FROM lpecom_films f
INNER JOIN lpecom_realisateurs r ON f.id_realisateur = r.id
ORDER BY f.id ASC;
```

Cette requête affiche l'id et le nom du film, ainsi que le nom et le prénom du réalisateur, rangés par ordre croissant par rapport à l'id, s'il a un réalisateur renseigné.

- Resultat :

| id  | film                | prenom | nom       |
|-----|---------------------|--------|-----------|
| 121 | Requiem for a Dream | Darren | Aronofsky |
| 546 | Gladiator           | Ridley | Scott     |
| 775 | Blade Runner        | Ridley | Scott     |
| 984 | Seul sur Mars       | Ridley | Scott     |
| 986 | Black Swan          | Darren | Aronofsky |
| 987 | Wonder Woman        | Patty  | Jenkins   |

<br>

## Exercice 4
_Quel est le résultat de la requête ci-dessous ?_

```
SELECT f.id, f.nom AS film, r.prenom, r.nom
FROM lpecom_films f
LEFT JOIN lpecom_realisateurs r ON f.id_realisateur = r.id
ORDER BY f.id ASC;
```

Cette requête affiche l'id et le nom du film, ainsi que le nom et le prénom du réalisateur, rangés par ordre croissant par rapport à l'id, même s'il n'y a pas de réalisateur renseigné.

- Resultat :

| id  | film                | prenom | nom       |
|-----|---------------------|--------|-----------|
| 121 | Requiem for a Dream | Darren | Aronofsky |
| 546 | Gladiator           | Ridley | Scott     |
| 666 | Fight Club          | NULL   | NULL      |
| 775 | Blade Runner        | Ridley | Scott     |
| 984 | Seul sur Mars       | Ridley | Scott     |
| 986 | Black Swan          | Darren | Aronofsky |
| 987 | Wonder Woman        | Patty  | Jenkins   |
| 988 | The Tomorrow Man    | NULL   | NULL      |

<br>

## Exercice 5
_Quel est le résultat de la requête ci-dessous ?_

```
SELECT f.id, f.nom, fn.note
FROM lpecom_films f
LEFT JOIN lpecom_films_notes fn ON f.id = fn.id_film
ORDER BY f.id ASC;
```

Cette requête affiche l'id, le nom, et la note des films, rangés par ordre croissant d'id, même si le film ne possède pas de note.

- Resultat :

| id  | nom                 | note |
|-----|---------------------|------|
| 121 | Requiem for a Dream |    1 |
| 546 | Gladiator           |  4.5 |
| 546 | Gladiator           |  2.5 |
| 666 | Fight Club          |  4.2 |
| 775 | Blade Runner        |    5 |
| 984 | Seul sur Mars       |  3.5 |
| 986 | Black Swan          |  4.3 |
| 986 | Black Swan          |    3 |
| 987 | Wonder Woman        |  3.1 |
| 988 | The Tomorrow Man    | NULL |

<br>

## Exercice 6
_Quel est le résultat de la requête ci-dessous ?_

```
SELECT f.nom, r.prenom AS realisateur_prenom, r.nom AS realisateur_nom, AVG(fn.note) AS
moyenne_note
FROM lpecom_films f
INNER JOIN lpecom_realisateurs r ON f.id_realisateur = r.id
INNER JOIN lpecom_films_notes fn ON f.id = fn.id_film
WHERE f.id = 546;
```

Cette requête affiche le nom des film, les nom et prénom du réalisateur, et la note moyenne du film dont l'id = 546.

- Resultat :

| nom       | realisateur_prenom | realisateur_nom | ASmoyenne_note |
|-----------|--------------------|-----------------|----------------|
| Gladiator | Ridley             | Scott           |            3.5 |

<br>

## Exercice 7
_Quel est le résultat de la requête ci-dessous ?_

```
SELECT r.nation, AVG(fn.note) AS moyenne_note
FROM lpecom_films f
INNER JOIN lpecom_realisateurs r ON f.id_realisateur = r.id
INNER JOIN lpecom_films_notes fn ON f.id = fn.id_film
WHERE r.nation = 'us';
```

Cette requête affiche la nationnalité des réalisateurs et la moyenne des notes des films issus de réalisateurs d'origine US.

- Resultat :

| nation | moyenne_note      |
|--------|-------------------|
| us     | 2.850000023841858 |

<br>

## Exercice 8
_Quel est le résultat de la requête ci-dessous ?_

```
SELECT r.nation, MAX(fn.note) AS max_note
FROM lpecom_films f
INNER JOIN lpecom_realisateurs r ON f.id_realisateur = r.id
INNER JOIN lpecom_films_notes fn ON f.id = fn.id_film
WHERE r.nation = 'uk';
```

Cette requête affiche la nationnalité et la note maximale des films issus de réalisateur originaire du Royaume-Unis.

| nation | max_note |
|--------|----------|
| uk     |        5 |


</details>
