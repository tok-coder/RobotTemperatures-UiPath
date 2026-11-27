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

Lecture du fichier Excel. Au début, j'ai utilisé l'activité Use Excel File, mais le robot n'arrivait pas à ouvrir la feuille. Cette activité a besoin de l'application Excel pour fonctionner, et la version d'Excel installée sur mon ordinateur n'était pas activée. J'ai donc utilisé Read Range Workbook, qui lit le fichier directement sans ouvrir Excel. Ça a réglé le problème.

Portée des variables. J'ai eu plusieurs fois l'erreur « is not declared ». En fait, mes variables avaient été créées à l'intérieur d'un bloc et n'étaient pas visibles ailleurs. J'ai appris à vérifier la portée dans le Data Manager et à bien placer mes activités.

Réponse de l'API. Quand j'ai affiché la réponse de HTTP Request, j'obtenais « HttpResponseSummary » au lieu des données. La sortie était un objet et non du texte. J'ai utilisé .TextContent pour récupérer le JSON et extraire la température.

## Auteure

Kardiata Ly dite Tokossel Mbodj – étudiante au baccalauréat en informatique, UQTR
