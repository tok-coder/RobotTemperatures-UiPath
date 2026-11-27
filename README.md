# RobotTemperatures-UiPath

Robot UiPath qui récupère la température actuelle de cinq villes du Québec à partir de l'API Open-Meteo et enregistre les résultats dans un fichier Excel.

Projet personnel réalisé pour apprendre l'automatisation (RPA) avec UiPath Studio.

## Fonctionnement

1. Lecture des villes et de leurs coordonnées dans `villes.xlsx`
2. Appel de l'API Open-Meteo (requête HTTP GET) pour chaque ville
3. Lecture de la réponse JSON pour extraire la température
4. Ajout de chaque résultat dans un tableau (ville, température, heure, statut)
5. Écriture du tableau dans `resultats.xlsx`

Si l'appel échoue pour une ville, l'erreur est enregistrée dans le fichier de résultats et le robot continue avec la ville suivante (Try Catch).

## Outils

UiPath Studio (VB.NET), HTTP Request, Deserialize JSON, DataTable, Read/Write Range Workbook, Try Catch, Log Message.

## Fichiers

- `Main.xaml` : workflow principal
- `project.json` : configuration du projet
- `villes.xlsx` : fichier d'entrée
- `resultats.xlsx` : exemple de résultat

## Exécution

Ouvrir le projet dans UiPath Studio, vérifier que `villes.xlsx` est fermé, puis lancer Run File.

## Difficultés rencontrées

[À écrire avec vos mots. Par exemple : ce qui n'a pas marché avec Use Excel File et pourquoi vous êtes passée aux activités Workbook ; la portée des variables ; la sortie de HTTP Request qui était un objet et non du texte.]

## Auteure

Kardiata Ly dite Tokossel Mbodj – étudiante au baccalauréat en informatique, UQTR
