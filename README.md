# Bases de données avancées

# L'objectif du projet
 Ce projet consiste a travailler sur Deux déffirentes APIs qui ont un lien entre et avec lesquelles on va  construire une bases de données et arriver et emerger entre elles avec des requettes 
 
# Les APIs:
Les APIs choisies sont en Open Data et a trouver dans le site des APIs gouvernement : https://api.gouv.fr

# 1ère API : Découpage Administratif - (API Geo)

 Source de l'API :https://api.gouv.fr/les-api/api-geo
 
 Description

L' API Découpage Administratif fait partie de la boîte-à-outils API Géo. Elle permet d'interroger facilement les référentiels géographique nationaux.
A quoi sert l'API Découpage Administratif ?

En intégrant l'API dans votre système d'information, vous pouvez notamment :

   rechercher une communes par nom, code postal ou coordonnées géographiques
   rechercher un département par son nom
   rechercher une région par son nom
   
   L'apercu de l'API
   ![image](https://user-images.githubusercontent.com/85731154/133302724-e44c2c20-4c1d-4e85-945d-7fb5d4dd57e3.png)

Présentation du code:

On a créé une fonction nommée apiToDatabase qui regroupe toutes les étapes a suivre pour obtenir le résultat final, Elle retourne à la fin un dataframe et on le compare à la base des données crées

![image](https://user-images.githubusercontent.com/85731154/133302907-b34d56ed-515f-4073-b3b0-7773dcfae5dd.png)

Le dictionaire Obtenu :

![image](https://user-images.githubusercontent.com/85731154/133304069-900c0f91-f722-4ee5-aedf-852715f9587a.png)

les résultats :

![image](https://user-images.githubusercontent.com/85731154/133304208-57ccd7a1-0535-4c8b-a808-d15b368c96c8.png)

Après avoir récupérer les données de l’api on va procéder à la création de la base de données dans sql server

Le code suivant va nous permettre de réaliser cette étape:

![image](https://user-images.githubusercontent.com/85731154/133304299-84469323-f7d9-49ba-8606-380c62e39845.png)


# 2ème API : La Bonne Alternance - (API LBA)

 Source de l'API: https://labonnealternance.apprentissage.beta.gouv.fr/api-docs/swagger.json
 
 Description

L’API La Bonne Alternance permet d’exposer les deux composantes de l'apprentissage : la formation et l'emploi. Ce service permet d’exposer également les entreprises susceptibles de recruter sur l'ensemble du périmètre Alternance. Le site La Bonne Alternance  donne un aperçu visuel de ces données.

A quoi sert l'API La Bonne Alternance ?

L’API La Bonne Alternance sert à offrir une information complète et centralisée aux publics en recherche d’une formation en apprentissage et/ou d’un contrat en alternance.

En tant qu’opérateur public ou privé traitant des questions d’orientation, de formation ou d’emploi en général, et d’alternance (apprentissage, professionnalisation) en particulier, il est possible de récupérer indépendamment ou simultanément les données :

   formations en apprentissage
   offres d’emploi en apprentissage
   entreprises présentant un fort potentiel de recrutement en alternance

Selon l’API sélectionnée, ces données sont récupérables pour :

   un secteur géographique (point géographique, département, région ou France entière)
   un secteur professionnel (domaine ou ensemble de domaines professionnels ou tous domaines professionnels)
   un métier ou ensemble de métiers définis
 
 Aperçu de l'APi

1
Présentation du code:

On a créé une fonction nommée apiToDatabase qui regroupe toutes les étapes a suivre pour obtenir le résultat final, Elle retourne à la fin un dataframe et on le compare à la base de données crée . 2
Aperçu du dictionnaire obtenu :
3
Aperçu du dataframe obtenu :
Capture

Après avoir récupérer les données de l’api on va procéder à la création de la base de données dans sql server

Le code suivant va nous permettre de réaliser cette étape:

5

Ensuite on va créer une table avec les colonnes de l’api comme présenté ci-dessous

6


Finalement on va remplir la base de données crée précédemment grâce à une boucle qui transmettra toutes les données dans la base de données.

La raquette qui remplit la base de données:

cursor.executemany("INSERT INTO region (nom, code,codeDepartement,codeRegion,codesPostaux,populationR) VALUES (?,?,?,?,?,?)", Table)
7

La fonction conv:

Cette fonction va nous aider à convertir certaine colonnes afin de faciliter l’insertion dans la base de données et éviter certaines erreurs.
8

A la fin de l’exécution on peut vérifier notre base de données dans sql server


9

Présentation du fonctionnement final :
