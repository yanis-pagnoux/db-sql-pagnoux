# Réservation de matériel 

## Présentation du projet
Dans cet exercice, nous allons créer une base de données pour gérer la réservation de matériel pour une école d'ingénieur. La base de données contiendra des informations sur les étudiants, le matériel disponible et les réservations effectuées

## Consignes de rendu
### Date 
À définir lors du premier TP. 

### Format 
1 Fichier contenant les éléments d’analyses demandés en première partie :
1. Analyse des besoins
2. Modélisation des données
3. Modélisation logique

1 dossier contenant 1 script par exercice. Les fichiers devront être nommés comme suit 
1. 2024_BDD_NOM_PRENOM_EX3
2. 2024_BDD_NOM_PRENOM_EX1_2 ; (pour les sous-parties)

Ces fichiers devront se trouver sur un référentiel public GIT.
vous devrez juste envoyer le lien du GIT en fin de TP à alexandre.touret@univ-tours.fr avec comme Objet : [BDD4][Nom][Prenom] - Rendu de TP


## Analyse des besoins

Identifiez les entités principales impliquées dans le système de réservation de matériel, par exemple : Utilisateur, Matériel, Réservation. Identifiez les attributs nécessaires pour chaque entité, en tenant compte des informations à stocker et à gérer, par exemple : nom, prénom, email pour Utilisateur. Identifiez les associations entre les entités, par exemple : une Réservation est liée à un Utilisateur et à un Matériel.

## Modélisation des données
Utilisez les symboles MERISE pour représenter les entités, les attributs et les associations identifiées. Dessinez un schéma entité-association (ER) représentant les entités, les attributs et les associations, ainsi que les cardinalités entre elles. Identifiez les clés primaires pour chaque entité. 

## Modélisation logique

Transformez le schéma entité-association (ER) en un schéma relationnel utilisant les tables pour représenter les entités et les associations. Identifiez les clés primaires et les clés étrangères nécessaires pour définir les relations entre les tables. Documentez le schéma relationnel en spécifiant les types de données appropriés pour chaque attribut. 

## Conception de la base de données
La base de données peut être créée en utilisant un logiciel de gestion de base de données relationnelle. Dans le cadre de ce TP, nous utiliserons PostgreSQL.

## Implémentation de la base de données

Après avoir conçu la base de données, mettez en place en créant les tables et les contraintes de clé étrangère. Les exercices ci-dessous vous permettront de mettre en place des requêtes avec des niveaux de difficultés progressives. 

## Exercice 1

Insérez des données dans les tables pour créer des utilisateurs, du matériel, des réservations et des emprunts. 

Effectuez des requêtes SELECT pour vérifier que les données ont bien été insérées. 

### Ajout de données dans la table « Utilisateur » 

1. Proposez un contenu de la table utilisateur (et documentez le) 
2. Créez la table Utilisateur 
3. Complétez là avec au moins 10 lignes 

### Ajout de données dans la table « Matériel »

1. Proposez un contenu de la table matériel (et documentez le) 
2. Créez la table Matériel 
3. Complétez là avec au moins 10 lignes 

### Ajout de données dans la table « Réservation » 
1. Proposez un contenu de la table réservation (et documentez le) 
2. Une réservation est encadrée par une date de début et une date de fin, proposez le tableau de description. 
3. Créez la table Reservation 
4. Complétez là avec au moins 5 lignes

## Exercice 2 : Effectuer des requêtes de sélection

Effectuez des requêtes SELECT pour récupérer des informations sur les utilisateurs, le matériel, les réservations et les emprunts. Utilisez des clauses ``WHERE``  pour filtrer les résultats en fonction de critères spécifiques. 

> aside: negative
> Au moins 3 requêtes sont attendues (avec au moins une par table et comprenant des clauses ``WHERE``)
>
 
## Exercice 3 : Effectuer des requêtes de jointure 

Effectuez des requêtes de jointure pour combiner les données de plusieurs tables. 

> aside: positive
> Exemple : Récupérez les informations sur les utilisateurs ayant effectué une réservation donnée, ou encore les informations sur le matériel emprunté par un utilisateur donné. 
>

1. Une requête de jointure sur les utilisateurs ayant effectué une réservation 
2. Une requête de jointure pour récupérer les informations sur le matériel emprunté par un utilisateur donné 

## Exercice 4 : Effectuer des requêtes d'agrégation

Effectuez des requêtes d'agrégation pour calculer des statistiques sur les données.

> aside: positive
> Exemple : Calculez le nombre total de réservations effectuées sur une période donnée, ou encore le nombre d'utilisateurs ayant emprunté du matériel donné. 
>

1. Requête d’aggrégation pour calculer le nombre total de réservations effectuées sur une période donnée 
2. Requête d’aggrégation pour calculer le nombre d’utilisateur ayant emprunté du matériel 

## Exercice 5 : Mettre à jour les données 

Effectuez des requêtes ``UPDATE`` pour mettre à jour les données dans les tables. 

> aside: positive
> Exemple : Modifiez la quantité disponible d'un matériel après un emprunt, ou encore annuler une réservation existante. 
>

Requête de modification de la quantité disponible d’un matériel après un emprunt

## Exercice 6 : Supprimer des données 

Effectuez des requêtes DELETE pour supprimer des données dans les tables. 
> aside: positive
> Exemple : supprimez une réservation existante ou encore retirer un utilisateur du système.
>

1. Requête de suppression d’une réservation existante
 
 
## Exercice 7 : Requêtes avancées

Effectuer les requêtes suivantes : 

1. Afficher tous les utilisateurs ayant emprunté au moins un équipement 
2. Afficher les équipements n’ayant jamais été empruntés 
3. Afficher les équipements ayant été emprunté plus de 3 fois 
4. Afficher le nombre d’emprunt pour chaque utilisateur 

> aside: positive
> Aide : Assurez-vous d’avoir tous les pré-requis avant de penser à tester vos requêtes.
>

## Exercice 8 : Gestion des réservations avec contraintes de disponibilité
### Contexte
nous souhaitons ajouter des contraintes de disponibilité sur les réservations de matériel. Un matériel ne peut être réservé que s'il est disponible pendant la période spécifiée. Après avoir terminé le TP de “base”, vous devez mettre à jour le schéma de la base de données et implémenter les fonctionnalités nécessaires pour gérer ces contraintes.

### Instructions

1. Mettez à jour le modèle de données existant en ajoutant une nouvelle table "disponibilite" avec les colonnes suivantes : 

* ``id_disponibilite`` (clé primaire)
* ``id_materiel`` (clé étrangère référençant la table "materiel") 
* ``date_debut`` (date de début de la disponibilité) 
* ``date_fin`` (date de fin de la disponibilité) 

2. Modifiez la table "reservation" en ajoutant une nouvelle colonne "id_disponibilite" (clé étrangère référençant la table "disponibilite"). 

3. Modifiez les contraintes SQL existantes pour prendre en compte les contraintes de disponibilité lors de la création et de la mise à jour des réservations. 

4. Implémentez une fonctionnalité permettant de vérifier la disponibilité d'un matériel pour une période donnée avant de permettre la réservation. Si le matériel n'est pas disponible, affichez un message d'erreur approprié. 

5. Implémentez une fonctionnalité permettant de gérer les disponibilités du matériel. Les administrateurs doivent pouvoir ajouter, modifier et supprimer des périodes de disponibilité pour chaque matériel. 

6. Testez votre application en effectuant des réservations avec différentes périodes pour vérifier que les contraintes de disponibilité sont correctement appliquées.

 
## Exercice 9 : Gestion des retours de matériel avec contrôle des retards
### Contexte
Nous souhaitons ajouter des fonctionnalités de gestion des retours de matériel avec contrôle des retards. Lorsqu'un étudiant rend du matériel emprunté, il doit signaler le retour dans la base de données. Si le matériel est rendu en retard, des pénalités peuvent être appliquées. Vous devez être en mesure de vérifier s'ils ont des retours en retard et le cas échéant, le montant des pénalités encourues.
### Instructions

1.	Mettez à jour le modèle de données existant en ajoutant une nouvelle table "RetourMatériel" avec les colonnes suivantes :
``id_retour`` (clé primaire)
``id_reservation`` (clé étrangère référençant la table "Reservation")
``date_retour`` (date à laquelle le matériel a été rendu)
``retard`` (indicateur de retard, par exemple, un booléen)
2.	Modifiez la table "Reservation" en ajoutant une nouvelle colonne "date_retour_effectif" pour enregistrer la date à laquelle le matériel a été rendu.

3.	Modifiez les contraintes SQL existantes pour prendre en compte les retours de matériel et les retards éventuels lors de la mise à jour des réservations.

4.	Implémentez une fonctionnalité permettant de calculer automatiquement le retard sur le retour du matériel, si applicable.

5.	Implémentez une fonctionnalité permettant de vérifier si un retour est en retard et d'afficher le montant des pénalités, le cas échéant.
Testez votre application en effectuant des retours de matériel, certains à l'heure et d'autres en retard, pour vérifier que les contraintes sont correctement appliquées et que les pénalités sont calculées de manière appropriée.


## Exercice 10: Full scan et index
### Contexte
Nous allons simuler les effets indésirables liés au traitement d'un grand volume de données. Dans le cadre de cet exercice, nous nous aurons à analyser et trouver une solution pour accélérer le traitement d'une requête SQL.

### Instructions

1. Aller dans VS Code, ouvrez un terminal et tapez la commande suivante:

```bash
sudo apt update
sudo apt install postgresql-client
``` 

2. Créez les scripts python suivants et copiez les à la racine du projet

3. Exécutez les scripts

4. Importez les fichiers CSV dans la base. Pour chaque table, exécutez la commande SQL ``COPY`` vous permettant d'insérer des données dans une table à partir d'un fichier CSV.

Pour le faire à distance, nous utiliserons la commande ``psql`` qui lira le contenu du fichier depuis l' entrée standard (``STDIN``).

Indications:
* L' hôte distant est disponible dans PgAdmin dans les paramètres du serveur.
* L'utilisateur et mot de passe est ``polytech``.

5. Exécutez une recherche impliquant des  jointures entre les tables:
* Matériel
* Réservation
* Utilisateur

Faites une recherche en vous basant comme critère sur une des colonnes de la table de réservation (ex. la date de réservation).

6. Affichez le plan d' exécution de la requête à l'aide de l'instruction ``EXPLAIN``. Analysez et indiquez la cause du ralentissement.

7. Créer un index pour le champ en question

8. Relancez la requête et affichez une nouvelle fois le plan d'exécution.