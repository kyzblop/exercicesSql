### Exercices SQL
Il s'agit d'une suite d'exercices sur une base SQL afin de pratiquer les requête SQL

Prérequis : Créer une base de données (ici : "lpecom_bdd"), importer les données et l'utiliser (requête : use lpecom_bdd;)

# Partie 1/
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

# Partie 2/
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



