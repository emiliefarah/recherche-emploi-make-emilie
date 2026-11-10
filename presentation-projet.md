# Présentation du projet — Veille automatisée d'offres d'emploi Data Analyst

## 1. Objectif du projet

L'objectif de ce projet est de mettre en place une automatisation permettant de rechercher des offres d'emploi dans le domaine de la Data, de les enregistrer dans un tableau Google Sheets et d'envoyer des notifications sur Discord.

Cette automatisation permet de centraliser les offres et de faciliter le suivi des candidatures, sans avoir à effectuer manuellement les mêmes recherches chaque semaine.

## 2. Outils utilisés

- **Make** : création et exécution du scénario d'automatisation.
- **JSearch API** : recherche et récupération des offres d'emploi.
- **Google Sheets** : enregistrement des offres et suivi des candidatures.
- **Discord** : réception des notifications contenant les nouvelles offres.
- **GitHub** : documentation et partage du projet.

## 3. Fonctionnement de l'automatisation

Le scénario Make est composé de quatre modules :

1. **HTTP — GET (JSearch)** : interroge l'API JSearch pour récupérer des offres d'emploi.
2. **Iterator** : traite individuellement les offres renvoyées par l'API.
3. **Google Sheets — Add a Row** : ajoute chaque offre dans une nouvelle ligne du tableau.
4. **HTTP — POST (Discord)** : envoie une notification contenant les informations de l'offre dans un salon Discord.

Les informations récupérées comprennent notamment le titre du poste, le nom de l'entreprise, le lieu, le type de contrat, la date de publication et le lien pour postuler.

Le tableau Google Sheets contient également des colonnes permettant de suivre le statut des candidatures, la date de candidature et des notes personnelles.

## 4. Planification

Le scénario est activé et programmé pour s'exécuter automatiquement :

- **Fréquence :** chaque semaine
- **Jour :** lundi
- **Heure :** 8 h
- **Fuseau horaire :** Europe/Paris

## 5. Difficultés rencontrées et solutions

### Mapping des données dans Google Sheets

Après les explications du formateur, le fonctionnement général de Make était assez simple à comprendre.

La principale difficulté a été d'identifier les bonnes variables à sélectionner dans le module *Add a Row*, afin que les informations récupérées par JSearch soient enregistrées dans les colonnes correspondantes.

**Solution :** apprendre à identifier les données renvoyées par l'API, les associer aux champs de Google Sheets et vérifier le résultat grâce aux tests.

### Construction des notifications Discord

La configuration des notifications Discord a été plus simple, mais nécessitait également de comprendre comment utiliser les variables.

**Solution :** construire un message contenant les informations importantes de chaque offre, puis tester son envoi pour vérifier sa lisibilité.

### Documentation GitHub

Une difficulté supplémentaire est apparue lors de l'ajout de la capture d'écran du scénario dans le README : l'image ne s'affichait pas correctement à cause d'un problème de nom de fichier et d'extension.

**Solution :** corriger le nom du fichier image et adapter son chemin dans le README.

## 6. Tests et résultats

Le 10 novembre 2026, un test manuel du scénario a permis de récupérer et de traiter **10 offres d'emploi**.

Les résultats ont été vérifiés :

- 10 offres enregistrées dans Google Sheets.
- 10 notifications reçues dans le salon Discord `#offres-data`.
- Liens vers les offres présents dans les deux destinations.
- Scénario exécuté avec succès en 19 secondes.

Le test confirme le bon fonctionnement de la chaîne d'automatisation, depuis la recherche des offres jusqu'à leur diffusion.

## 7. Consommation et estimation

Lors du dernier test :

| Indicateur | Résultat |
|---|---|
| Offres traitées | 10 |
| Durée d'exécution | 19 secondes |
| Crédits Make consommés | 22 |
| Requêtes JSearch estimées | 1 |

Avec une exécution chaque lundi et en supposant 10 offres traitées par exécution :

| Période | Crédits Make estimés | Requêtes JSearch estimées |
|---|---:|---:|
| Une semaine | 22 | 1 |
| Quatre semaines | 88 | 4 |
| Une année (52 semaines) | 1 144 | 52 |

La consommation réelle dépend du nombre d'offres traitées et des éventuelles modifications du scénario.

## 8. Améliorations possibles

Plusieurs évolutions pourraient être envisagées :

- Filtrer davantage les offres pour privilégier les postes Data Analyst adaptés à un profil débutant.
- Éviter l'ajout de doublons dans Google Sheets.
- Ajouter des filtres sur les types de contrats.
- Améliorer le suivi des candidatures et leur statut.

## 9. Conclusion

Ce projet m'a permis de découvrir et de pratiquer l'automatisation avec Make, l'utilisation d'une API, le mapping des données et la transmission d'informations entre plusieurs outils.

J'ai notamment appris à comprendre les données renvoyées par une API et à les utiliser pour remplir automatiquement un tableau ou construire des notifications.

Le scénario est aujourd'hui fonctionnel, testé et programmé pour une exécution hebdomadaire.

## 10. Liens du projet

**Dépôt GitHub :**  
https://github.com/emiliefarah/veille-emploi-data-analyst

**Tableau Google Sheets :**  
https://docs.google.com/spreadsheets/d/11wb-PJj4ot1FI0GdJWXY6zHo2sXppyL0U_S5usa4sBQ/edit?usp=sharing
