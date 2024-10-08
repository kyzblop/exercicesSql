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

<br>

</details>

<details>
  <summary>
    Partie 4
  </summary>

## Exercice 1
_Quelle requête utiliser pour retrouver la ville qui possède les coordonnées GPS suivantes :
48.66913724637683, 1.87586057971015 ?_

- Requête à saisir :

```
select name from lpecom_cities where gps_lat = 48.66913724637683 and gps_lng = 1.87586057971015;
```

- Resultat :

| name                        |
|-----------------------------|
| Vieille-Eglise-en-Yvelines  |

<br>

## Exercice 2
_Sans jointure, quelle requête utiliser pour calculer le nombre de villes que compte le département de
l'Essonne ?_

- Requête à saisir :

```
select count(distinct name) from lpecom_cities where department_code = 91;
```

- Resultat :

| count(name) |
|-------------|
|         196 |

<br>

## Exercice 3
_Sans jointure, quelle requête utiliser pour calculer le nombre de villes en Île-de-France se terminant
par '-le-Roi' ?_

- Requête à saisir :

```
select count(distinct name) from lpecom_cities where department_code in (75, 77, 78, 91, 92, 93, 94, 95) and name like '%-le-Roi';
```

- Resultat :

| count(distinct name) |
|----------------------|
|                   11 |

<br>

## Exercice 4
_Combien de villes possèdent le code postal (zip_code) 77320 ? Renommez la colonne de résultat
n_cities._

- Requête à saisir :

```
select count(distinct name) as n_cities from lpecom_cities where zip_code = 77320;
```

- Resultat :

| n_cities |
|----------|
|       22 |

<br>

## Exercice 5
_Sans jointure, quelle requête utiliser pour calculer le nombre de villes commençant par 'Saint-' en
Seine-et-Marne ?_

- Requête à saisir :

```
select count(distinct name) from lpecom_cities where department_code = 77 and name like 'Saint-%';
```

- Resultat :

| count(distinct name) |
|----------------------|
|                   36 |

<br>

## Exercice 6
_Quelles villes possèdent un code postal (zip_code) compris entre 77210 et 77810 ?_

- Requête à saisir :

```
select name from lpecom_cities where zip_code between 77210 and 77810;
```

- Resultat :

| name                        |
|-----------------------------|
| Achères-la-Forêt            |
| Amponville                  |
| Andrezel                    |
|...|
| Voulangis                   |
| Voulton                     |
| Yèbles                      |

La requête affiche 317 lignes de resultat, le tableau a donc été tronqué ici.

<br>

## Exercice 7
_Sans jointure, quelles sont les deux villes de Seine-et-Marne à avoir le code postal (zip_code) le
plus grand ?_

- Requête à saisir :

```
select name, zip_code from lpecom_cities where department_code = 77 order by zip_code desc  limit 2;
```

- Resultat :

| name             | zip_code |
|------------------|----------|
| Mauregard        | 77990    |
| Le Mesnil-Amelot | 77990    |

<br>

## Exercice 8
_Quel est le code postal (zip_code) le plus grand de la table lpecom_cities ?_

- Requête à saisir :

```
select max(zip_code) from lpecom_cities;
```

- Resultat :
- 
| max(zip_code) |
|---------------|
| 95880         |

<br>

## Exercice 9
_Avec un seul WHERE et aucun OR, quelle est la requête permettant d'afficher les départements des
régions ayant le code suivant : 75, 27, 53, 84 et 93 ? Le résultat doit afficher le nom du département
ainsi que le nom et le slug de la région associée._

- Requête à saisir :

```
select d.name as Departement, r.name as Region, r.slug from lpecom_departments d
inner join lpecom_regions r on d.region_code = r.code where r.code in (75, 27, 53, 84, 93);
```

- Resultat :

| Departement             | Region                      | slug                      |
|-------------------------|-----------------------------|---------------------------|
| Côte-d'Or               | Bourgogne-Franche-Comté     | bourgogne franche comte   |
| Doubs                   | Bourgogne-Franche-Comté     | bourgogne franche comte   |
| Jura                    | Bourgogne-Franche-Comté     | bourgogne franche comte   |
| Nièvre                  | Bourgogne-Franche-Comté     | bourgogne franche comte   |
| Haute-Saône             | Bourgogne-Franche-Comté     | bourgogne franche comte   |
| Saône-et-Loire          | Bourgogne-Franche-Comté     | bourgogne franche comte   |
| Yonne                   | Bourgogne-Franche-Comté     | bourgogne franche comte   |
| Territoire de Belfort   | Bourgogne-Franche-Comté     | bourgogne franche comte   |
| Côtes-d'Armor           | Bretagne                    | bretagne                  |
| Finistère               | Bretagne                    | bretagne                  |
| Ille-et-Vilaine         | Bretagne                    | bretagne                  |
| Morbihan                | Bretagne                    | bretagne                  |
| Charente                | Nouvelle-Aquitaine          | nouvelle aquitaine        |
| Charente-Maritime       | Nouvelle-Aquitaine          | nouvelle aquitaine        |
| Corrèze                 | Nouvelle-Aquitaine          | nouvelle aquitaine        |
| Creuse                  | Nouvelle-Aquitaine          | nouvelle aquitaine        |
| Dordogne                | Nouvelle-Aquitaine          | nouvelle aquitaine        |
| Gironde                 | Nouvelle-Aquitaine          | nouvelle aquitaine        |
| Landes                  | Nouvelle-Aquitaine          | nouvelle aquitaine        |
| Lot-et-Garonne          | Nouvelle-Aquitaine          | nouvelle aquitaine        |
| Pyrénées-Atlantiques    | Nouvelle-Aquitaine          | nouvelle aquitaine        |
| Deux-Sèvres             | Nouvelle-Aquitaine          | nouvelle aquitaine        |
| Vienne                  | Nouvelle-Aquitaine          | nouvelle aquitaine        |
| Haute-Vienne            | Nouvelle-Aquitaine          | nouvelle aquitaine        |
| Ain                     | Auvergne-Rhône-Alpes        | auvergne rhone alpes      |
| Allier                  | Auvergne-Rhône-Alpes        | auvergne rhone alpes      |
| Ardèche                 | Auvergne-Rhône-Alpes        | auvergne rhone alpes      |
| Cantal                  | Auvergne-Rhône-Alpes        | auvergne rhone alpes      |
| Drôme                   | Auvergne-Rhône-Alpes        | auvergne rhone alpes      |
| Isère                   | Auvergne-Rhône-Alpes        | auvergne rhone alpes      |
| Loire                   | Auvergne-Rhône-Alpes        | auvergne rhone alpes      |
| Haute-Loire             | Auvergne-Rhône-Alpes        | auvergne rhone alpes      |
| Puy-de-Dôme             | Auvergne-Rhône-Alpes        | auvergne rhone alpes      |
| Rhône                   | Auvergne-Rhône-Alpes        | auvergne rhone alpes      |
| Savoie                  | Auvergne-Rhône-Alpes        | auvergne rhone alpes      |
| Haute-Savoie            | Auvergne-Rhône-Alpes        | auvergne rhone alpes      |
| Alpes-de-Haute-Provence | Provence-Alpes-Côte d'Azur  | provence alpes cote dazur |
| Hautes-Alpes            | Provence-Alpes-Côte d'Azur  | provence alpes cote dazur |
| Alpes-Maritimes         | Provence-Alpes-Côte d'Azur  | provence alpes cote dazur |
| Bouches-du-Rhône        | Provence-Alpes-Côte d'Azur  | provence alpes cote dazur |
| Var                     | Provence-Alpes-Côte d'Azur  | provence alpes cote dazur |
| Vaucluse                | Provence-Alpes-Côte d'Azur  | provence alpes cote dazur |

<br>

## Exercice 10
_Quelle requête utiliser pour obtenir en résultat, les noms de la région, du département et de chaque
ville du département ayant pour code 77 ?_

- Requête à saisir :

```
select r.name as Region, d.name as Departement, c.name as Ville from lpecom_cities c
inner join lpecom_departments d on d.code = c.department_code
inner join lpecom_regions r on r.code = d.region_code
where d.code = 77;
```

- Resultat :

| Region         | Departement    | Ville                       |
|----------------|----------------|-----------------------------|
| Ile-de-France  | Seine-et-Marne | Achères-la-Forêt            |
| Ile-de-France  | Seine-et-Marne | Amillis                     |
| Ile-de-France  | Seine-et-Marne | Amponville                  |
| Ile-de-France  | Seine-et-Marne | Andrezel                    |
| Ile-de-France  | Seine-et-Marne | Annet-sur-Marne             |
| Ile-de-France  | Seine-et-Marne | Arbonne-la-Forêt            |
| Ile-de-France  | Seine-et-Marne | Argentières                 |
| ...|
| Ile-de-France  | Seine-et-Marne | Voulx                       |
| Ile-de-France  | Seine-et-Marne | Vulaines-lès-Provins        |
| Ile-de-France  | Seine-et-Marne | Vulaines-sur-Seine          |
| Ile-de-France  | Seine-et-Marne | Yèbles                      |

La requête affiche 510 lignes de resultat, le tableau a donc été tronqué ici.

<br>

</details>

<details>
  <summary>
    Partie 5
  </summary>


## Exercice 1
_Quelle requête utiliser pour afficher toutes les données de vaccination uniquement pour le 1er avril
2021 ?_

- Requête à saisir :

```
select * from lpecom_covid where jour = '2021-04-01';
```

- Resultat :

| id   | id_region | jour       | n_dose1 | n_dose2 | n_cum_dose1 | n_cum_dose2 | couv_dose1 | couv_dose2 |
|------|-----------|------------|---------|---------|-------------|-------------|------------|------------|
|   96 | 01        | 2021-04-01 |     425 |     160 |       10200 |        3834 |       2.70 |       1.00 |
|  197 | 02        | 2021-04-01 |     889 |     160 |       14579 |        5088 |       4.10 |       1.40 |
|  298 | 03        | 2021-04-01 |     331 |     267 |        9812 |        4550 |       3.40 |       1.60 |
|  399 | 04        | 2021-04-01 |     676 |     698 |       38033 |       20045 |       4.40 |       2.30 |
|  500 | 06        | 2021-04-01 |     191 |     106 |        9289 |        4304 |       3.30 |       1.50 |
|  601 | 07        | 2021-04-01 |      58 |      30 |         647 |         230 |       6.50 |       2.30 |
|  702 | 08        | 2021-04-01 |      55 |      45 |        1181 |         642 |       3.30 |       1.80 |
|  803 | 11        | 2021-04-01 |   42359 |   19709 |     1398310 |      400046 |      11.40 |       3.30 |
|  904 | 24        | 2021-04-01 |   11786 |    3071 |      328935 |      128834 |      12.90 |       5.00 |
| 1005 | 27        | 2021-04-01 |   13868 |    3758 |      426598 |      154511 |      15.30 |       5.60 |
| 1106 | 28        | 2021-04-01 |   17181 |    5110 |      483475 |      159637 |      14.60 |       4.80 |
| 1207 | 32        | 2021-04-01 |   17501 |   10004 |      819580 |      224681 |      13.70 |       3.80 |
| 1308 | 44        | 2021-04-01 |   22720 |    8593 |      791990 |      270775 |      14.40 |       4.90 |
| 1409 | 52        | 2021-04-01 |   18219 |    3305 |      465913 |      163045 |      12.30 |       4.30 |
| 1510 | 53        | 2021-04-01 |   17518 |    3965 |      478127 |      171912 |      14.30 |       5.10 |
| 1611 | 75        | 2021-04-01 |   33921 |    6380 |      899615 |      313916 |      15.00 |       5.20 |
| 1712 | 76        | 2021-04-01 |   32981 |    5157 |      823665 |      296753 |      13.90 |       5.00 |
| 1813 | 84        | 2021-04-01 |   35047 |    9568 |     1045812 |      348968 |      13.00 |       4.30 |
| 1914 | 93        | 2021-04-01 |   27929 |    7182 |      762341 |      253866 |      15.10 |       5.00 |
| 2015 | 94        | 2021-04-01 |    1593 |     650 |       61435 |       22805 |      17.80 |       6.60 |

<br>

## Exercice 2
_Quelle requête utiliser pour afficher toutes les données de vaccination uniquement pour le 1er avril
2021 avec le nom de la région concernée ?_

- Requête à saisir :

```
select c.*, r.name from lpecom_covid c left join lpecom_regions r on r.code = c.id_region where jour = '2021-04-01';
```

- Resultat :

| id   | id_region | jour       | n_dose1 | n_dose2 | n_cum_dose1 | n_cum_dose2 | couv_dose1 | couv_dose2 | name                        |
|------|-----------|------------|---------|---------|-------------|-------------|------------|------------|-----------------------------|
|   96 | 01        | 2021-04-01 |     425 |     160 |       10200 |        3834 |       2.70 |       1.00 | Guadeloupe                  |
|  197 | 02        | 2021-04-01 |     889 |     160 |       14579 |        5088 |       4.10 |       1.40 | Martinique                  |
|  298 | 03        | 2021-04-01 |     331 |     267 |        9812 |        4550 |       3.40 |       1.60 | Guyane                      |
|  399 | 04        | 2021-04-01 |     676 |     698 |       38033 |       20045 |       4.40 |       2.30 | La Réunion                  |
|  500 | 06        | 2021-04-01 |     191 |     106 |        9289 |        4304 |       3.30 |       1.50 | Mayotte                     |
|  601 | 07        | 2021-04-01 |      58 |      30 |         647 |         230 |       6.50 |       2.30 | NULL                        |
|  702 | 08        | 2021-04-01 |      55 |      45 |        1181 |         642 |       3.30 |       1.80 | NULL                        |
|  803 | 11        | 2021-04-01 |   42359 |   19709 |     1398310 |      400046 |      11.40 |       3.30 | Île-de-France               |
|  904 | 24        | 2021-04-01 |   11786 |    3071 |      328935 |      128834 |      12.90 |       5.00 | Centre-Val de Loire         |
| 1005 | 27        | 2021-04-01 |   13868 |    3758 |      426598 |      154511 |      15.30 |       5.60 | Bourgogne-Franche-Comté     |
| 1106 | 28        | 2021-04-01 |   17181 |    5110 |      483475 |      159637 |      14.60 |       4.80 | Normandie                   |
| 1207 | 32        | 2021-04-01 |   17501 |   10004 |      819580 |      224681 |      13.70 |       3.80 | Hauts-de-France             |
| 1308 | 44        | 2021-04-01 |   22720 |    8593 |      791990 |      270775 |      14.40 |       4.90 | Grand Est                   |
| 1409 | 52        | 2021-04-01 |   18219 |    3305 |      465913 |      163045 |      12.30 |       4.30 | Pays de la Loire            |
| 1510 | 53        | 2021-04-01 |   17518 |    3965 |      478127 |      171912 |      14.30 |       5.10 | Bretagne                    |
| 1611 | 75        | 2021-04-01 |   33921 |    6380 |      899615 |      313916 |      15.00 |       5.20 | Nouvelle-Aquitaine          |
| 1712 | 76        | 2021-04-01 |   32981 |    5157 |      823665 |      296753 |      13.90 |       5.00 | Occitanie                   |
| 1813 | 84        | 2021-04-01 |   35047 |    9568 |     1045812 |      348968 |      13.00 |       4.30 | Auvergne-Rhône-Alpes        |
| 1914 | 93        | 2021-04-01 |   27929 |    7182 |      762341 |      253866 |      15.10 |       5.00 | Provence-Alpes-Côte d'Azur  |
| 2015 | 94        | 2021-04-01 |    1593 |     650 |       61435 |       22805 |      17.80 |       6.60 | Corse                       |

<br>

## Exercice 3
_Quelle requête utiliser pour afficher le nombre au cumulé de vaccination première dose toutes
régions en 2020 ? Proposez également une solution pour les vaccination deuxième dose._

- Requête à saisir :

```
select sum(n_cum_dose1), sum(n_cum_dose2) from lpecom_covid where jour = '2020-12-31';
```

- Resultat :

| sum(n_cum_dose1) | sum(n_cum_dose2) |
|------------------|------------------|
|              374 |                0 |

<br>

## Exercice 4
_Quelle requête SQL utiliser pour afficher le nombre au cumulé de vaccination première dose pour la
région avec le code 93 uniquement pour le mois de mars 2021 ?_

- Requête à saisir :

```
select sum(n_dose1) from lpecom_covid where id_region = 93 and (jour like '2021-03-%');
```

- Resultat :

| sum(n_dose1) |
|--------------|
|       485530 |

<br>

## Exercice 5
_Quelle requête utiliser pour afficher le nombre au cumulé de vaccination deuxième dose pour la
région avec le code 11 uniquement pour le mois de mars 2021 ?_

- Requête à saisir :

```
select sum(n_dose2) from lpecom_covid where id_region = 11 and (jour like '2021-03-%');
```

- Resultat :

| sum(n_dose2) |
|--------------|
|       149931 |

<br>

## Exercice 6
_Quelle requête SQL utiliser pour afficher le record de vaccination première dose en une seule
journée ?
Avec une deuxième requête, afficher les informations de la région concernée, dont son nom, ainsi
que le jour du record._

- Requêtes à saisir :

```
select max(n_dose1) from lpecom_covid;

select r.*, c.jour from lpecom_regions r inner join lpecom_covid c on c.id_region = r.code where c.n_dose1 = 56661;
```

- Resultats :

| max(n_dose1) |
|--------------|
|        56661 |

| id | code | name           | slug          | jour       |
|----|------|----------------|---------------|------------|
|  6 | 11   | Île-de-France  | ile de france | 2021-03-26 |

<br>

## Exercice 7
_Quelle requête utiliser pour afficher le record de vaccination deuxième dose en une seule journée ?
Avec une deuxième requête, afficher les informations de la région concernée, dont son nom, ainsi
que le jour du record._

- Requêtes à saisir :

```
select max(n_dose2) from lpecom_covid;

select r.*, c.jour from lpecom_regions r inner join lpecom_covid c on c.id_region = r.code where c.n_dose2 = 21524;
```

- Resultats :

| max(n_dose2) |
|--------------|
|        21524 |

| id | code | name           | slug          | jour       |
|----|------|----------------|---------------|------------|
|  6 | 11   | Île-de-France  | ile de france | 2021-04-02 |

<br>

## Exercice 8
_Quelles requêtes permettent de connaitre quelle région possède la plus grande couverture de
vaccination avec une dose et deux doses ?
Vous aurez besoin de 4 requêtes pour répondre aux deux questions. Vous aurez besoin du résultat
de la première requête pour la deuxième._

- Requêtes à saisir :

Pour la première dose :
```
select max(couv_dose1) from lpecom_covid;

select r.name from lpecom_regions r inner join lpecom_covid c on c.id_region = r.code where c.couv_dose1 = 19.70;
```

Pour la seconde dose :

```
select max(couv_dose2) from lpecom_covid;

select r.name from lpecom_regions r inner join lpecom_covid c on c.id_region = r.code where c.couv_dose2 = 8.00;
```

- Resultats :

Pour la première dose :

| max(couv_dose1) |
|-----------------|
|           19.70 |

| name  |
|-------|
| Corse |

Pour la seconde dose :

| max(couv_dose2) |
|-----------------|
|            8.00 |

| name  |
|-------|
| Corse |

<br>

## Exercice 9
_Quelle requête utiliser pour afficher le nom de la région qui a le plus faible taux de couverture de
vaccination avec une dose ?
Vous aurez besoin de 2 requêtes pour répondre à la question._

- Requêtes à saisir :

```
select min(couv_dose1) from lpecom_covid where jour='2021-04-06';

select r.name from lpecom_regions r inner join lpecom_covid c on r.code = c.id_region where c.jour = '2021-04-06' and c.couv_dose1 = 2.80;
```

- Resultats :

| min(couv_dose1) |
|-----------------|
|            2.80 |

| name       |
|------------|
| Guadeloupe |

<br>

## Exercice 10
_Quelle requête utiliser pour calculer la couverture moyenne entre les différentes régions à la date la
plus récente, pour les vaccinations une et deux doses ?
Vous renommez les colonnes de résultats : couverture_dose1_avg et couverture_dose2_avg_

- Requête à saisir :

```
select avg(couv_dose1) as couverture_dose1_avg, avg(couv_dose2) as couverture_dose2_avg from lpecom_covid where jour='2021-04-06';
```

- Resultat :

| couverture_dose1_avg | couverture_dose2_avg |
|----------------------|----------------------|
|            11.425000 |             4.115000 |

<br>

## Exercice 11
_Quelle requête utiliser pour afficher les données de vaccination des régions (avec leur nom) qui
possèdent une couveture vaccinale supérieure à 15 %
pour la première dose et supérieure à 5 % pour la deuxième dose ?_

- Requête à saisir :

```
select c.*, r.name from lpecom_covid c inner join lpecom_regions r on c.id_region = r.code where c.couv_dose1 > 15 and (c.couv_dose2 > 5) and (c.jour = '2021-04-06');
```

- Resultat :

| id   | id_region | jour       | n_dose1 | n_dose2 | n_cum_dose1 | n_cum_dose2 | couv_dose1 | couv_dose2 | name                        |
|------|-----------|------------|---------|---------|-------------|-------------|------------|------------|-----------------------------|
| 1010 | 27        | 2021-04-06 |    8750 |    5673 |      452564 |      164656 |      16.30 |       5.90 | Bourgogne-Franche-Comté     |
| 1111 | 28        | 2021-04-06 |    9709 |    7044 |      521581 |      177864 |      15.80 |       5.40 | Normandie                   |
| 1313 | 44        | 2021-04-06 |   11863 |    9593 |      836877 |      294393 |      15.20 |       5.30 | Grand Est                   |
| 1515 | 53        | 2021-04-06 |   11720 |    5454 |      515527 |      183113 |      15.40 |       5.50 | Bretagne                    |
| 1616 | 75        | 2021-04-06 |   24230 |   10300 |      976357 |      333583 |      16.30 |       5.60 | Nouvelle-Aquitaine          |
| 1717 | 76        | 2021-04-06 |   20502 |    8909 |      893235 |      314350 |      15.10 |       5.30 | Occitanie                   |
| 1919 | 93        | 2021-04-06 |   19503 |    7831 |      823968 |      276597 |      16.30 |       5.50 | Provence-Alpes-Côte d'Azur  |
| 2020 | 94        | 2021-04-06 |    1412 |     873 |       67780 |       27561 |      19.70 |       8.00 | Corse                       |

<br>

</details>

<details>
  <summary>
    Partie 6
  </summary>

## Exercice 1
_Sans jointure, quelle requête SQL utiliser pour afficher toutes les données de vaccination du 14
février 2021 uniquement, pour le département de Seine-et-Marne (77) ?_

- Requête à saisir :

```
select * from lpecom_covid_vaccin where dep_code = 77 and (jour = '2021-02-14');
```

- Resultat :

| id   | dep_code | vaccin | jour       | n_dose1 | n_dose2 | n_cum_dose1 | n_cum_dose2 |
|------|----------|--------|------------|---------|---------|-------------|-------------|
|  354 | 77       |      1 | 2021-02-14 |       4 |      57 |       30268 |       11080 |
|  455 | 77       |      2 | 2021-02-14 |       0 |       0 |          11 |           0 |
|  556 | 77       |      3 | 2021-02-14 |       7 |       0 |         913 |           0 |
| 2576 | 77       |      0 | 2021-02-14 |      11 |      57 |       31192 |       11080 |

<br>

## Exercice 2
_Sans jointure, quelle requête SQL utiliser pour afficher le cumul de toutes les données de
vaccination pour tous les vaccins du 14 février 2021 uniquement, pour les départements de
l'Essonne (91) et de la Seine-et-Marne (77) ?_

```
select * from lpecom_covid_vaccin where jour = '2021-02-14' and (dep_code = 91 or dep_code = 77);
```

- Resultat :

| id   | dep_code | vaccin | jour       | n_dose1 | n_dose2 | n_cum_dose1 | n_cum_dose2 |
|------|----------|--------|------------|---------|---------|-------------|-------------|
|  354 | 77       |      1 | 2021-02-14 |       4 |      57 |       30268 |       11080 |
|  455 | 77       |      2 | 2021-02-14 |       0 |       0 |          11 |           0 |
|  556 | 77       |      3 | 2021-02-14 |       7 |       0 |         913 |           0 |
|  960 | 91       |      1 | 2021-02-14 |       8 |      90 |       32750 |        7808 |
| 1061 | 91       |      2 | 2021-02-14 |       0 |       0 |           0 |           0 |
| 1162 | 91       |      3 | 2021-02-14 |       0 |       0 |         890 |           0 |
| 2576 | 77       |      0 | 2021-02-14 |      11 |      57 |       31192 |       11080 |
| 2778 | 91       |      0 | 2021-02-14 |       8 |      90 |       33640 |        7808 |

<br>

## Exercice 3
_Sans jointure, quelle requête utiliser pour afficher la somme des vaccinations première dose
réalisées uniquement avec le vaccin AstraZeneka pour le mois de février 2021 pour le département
de la Seine-et-Marne (77) ?_

- Requête à saisir :

```
select sum(n_dose1) from lpecom_covid_vaccin where vaccin = 3 and dep_code = 77 and jour like '2021-02-%';
```

- Resultat :

| sum(n_dose1) |
|--------------|
|         3667 |

<br>

## Exercice 4
_Sans jointure, quelle requête utiliser pour afficher la somme des vaccinations deuxième dose
réalisées avec le vaccin AstraZeneka ou Moderna pour le mois de mars 2021 pour le département
de la Seine-et-Marne (77) ?_

- Requête à saisir :

```
select sum(n_dose2) from lpecom_covid_vaccin where vaccin in (2, 3) and dep_code = 77 and jour like '2021-03-%';
```

- Resultat :

| sum(n_dose2) |
|--------------|
|           32 |

<br>

## Exercice 5
_Sans jointure, quelle requête utiliser pour afficher le record de vaccination première dose avec un
type de vaccin en une seule journée ?
Avec une deuxième requête qui exploitera une jointure, afficher toutes les informations possibles
pour cette journée record et sur le type de vaccin._

- Requêtes à saisir :

```
select max(n_dose1) from lpecom_covid_vaccin where not vaccin = 0;

select v.*, t.nom from lpecom_covid_vaccin v inner join lpecom_covid_vaccin_type t on v.vaccin = t.id where v.n_dose1 = 7494;
```

- Resultats :

| max(n_dose1) |
|--------------|
|         7494 |

| id  | dep_code | vaccin | jour       | n_dose1 | n_dose2 | n_cum_dose1 | n_cum_dose2 | nom         |
|-----|----------|--------|------------|---------|---------|-------------|-------------|-------------|
| 279 | 75       |      3 | 2021-03-12 |    7494 |       2 |       62834 |          52 | AstraZeneka |

<br>

## Exercice 6
_Sans jointure, quelle requête utiliser pour afficher le record de vaccination deuxième dose avec un
type de vaccin en une seule journée ?
Avec une deuxième requête qui exploitera deux jointures, afficher toutes les informations possibles
pour cette journée record, sur le type de vaccin et sur le département._

- Requête à saisir :

```
select max(n_dose2) from lpecom_covid_vaccin where not vaccin = 0;

select v.*, t.nom, d.name from lpecom_covid_vaccin v inner join lpecom_covid_vaccin_type t on v.vaccin = t.id
inner join lpecom_departments d on v.dep_code = d.code where v.n_dose1 = 5046;
```

- Resultats :

| max(n_dose2) |
|--------------|
|         5046 |

| id  | dep_code | vaccin | jour       | n_dose1 | n_dose2 | n_cum_dose1 | n_cum_dose2 | nom         | name  |
|-----|----------|--------|------------|---------|---------|-------------|-------------|-------------|-------|
| 279 | 75       |      3 | 2021-03-12 |    7494 |       2 |       62834 |          52 | AstraZeneka | Paris |

<br>

## Exercice 7
_Quelle requête permet de savoir quel département possède le plus grand nombre d'injections
première dose pour le vaccin AstraZeneka ?
Avec une deuxième requête, afficher uniquement les colonnes suivantes : le nom du vaccin ; le jour ; le nom et le code du département ; le nombre cumulé d'injections._

- Requêtes à saisir :

```
select max(c.n_cum_dose1), d.name from lpecom_covid_vaccin c inner join lpecom_departments d on c.dep_code = d.code where c.vaccin = 3;

select v.nom as nomVaccin, c.jour, d.name as nomDep, d.code, c.n_cum_dose1 from lpecom_covid_vaccin c
inner join lpecom_covid_vaccin_type v on c.vaccin = v.id
inner join lpecom_departments d on c.dep_code = d.code
where c.n_cum_dose1 = 122709;
```

- Resultats :

| max(c.n_cum_dose1) | name  |
|--------------------|-------|
|             122709 | Paris |

| nomVaccin   | jour       | nomDep | code | n_cum_dose1 |
|-------------|------------|--------|------|-------------|
| AstraZeneka | 2021-04-06 | Paris  | 75   |      122709 |

<br>

## Exercice 8
_Quelle requête permet de savoir quel département a eu le moins de vaccinations première dose
POEC Java Sophia - septembre 2024 ----- Jaouad Assabbour
Initiation SQL - Exercices VI / Sixième partie
avec le vaccin COMIRNATY Pfizer/BioNTech ?
Avec une deuxième requête, afficher uniquement les colonnes suivantes : le nom du vaccin ; le jour ; le nom et le code du département ; le nombre cumulé d'injections._

- Requête à saisir :

```
select d.name as nomDep, c.n_cum_dose1 from lpecom_departments d
inner join lpecom_covid_vaccin c on d.code = c.dep_code
where c.jour = '2021-04-06' and c.vaccin = 1 order by n_cum_dose1 limit 1;

select v.nom , c.jour, d.name, d.code, n_cum_dose1 from lpecom_covid_vaccin c
inner join lpecom_departments d on d.code = c.dep_code
inner join lpecom_covid_vaccin_type v on v.id = c.vaccin
where c.n_cum_dose1 = 90832;
```
- Resultats :

| nomDep     | n_cum_dose1 |
|------------|-------------|
| Val-d'Oise |       90832 |

| nom                       | jour       | name       | code | n_cum_dose1 |
|---------------------------|------------|------------|------|-------------|
| COMIRNATY Pfizer/BioNTech | 2021-04-06 | Val-d'Oise | 95   |       90832 |

<br>

## Exercice 9
_Quelle requête permet de connaître la moyenne de vaccinations première dose dans tous les
départements pour le vaccin Moderna ?
Renommer la colonne de résultat avec avg_moderna._

- Requête à saisir :

```
select avg(n_dose1) as avg_moderna from lpecom_covid_vaccin where jour ='2021-04-06' and vaccin = 2;
```

- Resultat :

| avg_moderna |
|-------------|
|    662.8750 |

<br>

## Exercice 10
_Quelle requête utiliser pour afficher les départements (avec leur nom) qui possèdent un nombre
d'injections deuxième dose avec le vaccin Moderna supérieur à 9000
ou un nombre d'injections première dose avec le vaccin COMIRNATY Pfizer/BioNTech supérieur à
120000 ? Vous aurez besoin de deux jointures._

- Requête à saisir :

```
select distinct d.name from lpecom_departments d
inner join lpecom_covid_vaccin c on c.dep_code = d.code
where (c.vaccin = 2 and c.n_cum_dose2 > 9000) or (c.vaccin = 1 and c.n_cum_dose1 > 120000);
```
- Resultat :

| name              |
|-------------------|
| Paris             |
| Hauts-de-Seine    |
| Seine-Saint-Denis |
| Val-de-Marne      |

<br>


</details>
