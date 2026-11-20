# Projet_td_Location_V-hicule_
Mini-projet Python : gestion d'une agence de localisation de véhicules (POO, menu console, sauvegarde JSON)
Sujet : Sujet 2 — Localisation de véhicules (console d'application, programmation orientée objet, sauvegarde JSON).

Participants : Audain Shelton et Woodly Rousseau

Description

Ce projet est une application console de gestion d'une agence de localisation. Elle permet d'enregistrer des véhicules (voitures et motos), des clients et des réservations, de suivre les départs et les retours, et de calculer le prix de chaque emplacement.

Les données sont sauvegardées dans un fichier JSON après chaque action et rechargées automatiquement au démarrage du programme.

Lancement

Le programme nécessite Python 3. Aucune bibliothèque externe n'est utilisée.

Pour le lancer, placer le fichier Python (devoir 1.py) et le fichier JSON dans le même dossier. Ensuite, ouvrez le fichier Python dans PyCharm et cliquez sur le bouton Run, ou le lancer depuis un terminal avec la commande : python "devoir 1.py".

Le menu s'affiche alors. Il suffit de taper le numéro d'une option puis d'appuyer sur Entrée. Taper 0 pour quitter.

Le fichier JSON fourni contient des données de démonstration. Pour repartir de zéro, il suffit de supprimer ce fichier : il sera recréé automatiquement.

Fonctionnalités

Le menu propose six actions : ajouter un véhicule (voiture ou moto), ajouter un client, faire une réservation, afficher la liste des réservations, enregistrer le départ d'un véhicule et enregistrer son retour. L'option 0 permet de quitter le programme.

Règles de gestion

Un même véhicule ne peut pas avoir deux réservations dont les périodes se croisent. Le jour de retour n'est pas compté : un véhicule rendu le jour 5 peut être reloué dès le jour 5. Le jour de fin doit toujours être après le jour de début.

Pour une voiture, le prix est le tarif journalier multiplié par le nombre de jours, avec 10 % de remise à partir de 7 jours. Pour une moto, c'est le tarif journalier multiplié par le nombre de jours, plus 10 de forfait.

En cas de retour tardif, chaque jour de retard est facturé 150 % du tarif journalier.

Une réservation passe par trois statuts : confirmée, puis en_cours au départ, puis termine au retour. Lorsqu'une opération est refusée, un message s'affiche et aucune donnée n'est modifiée.

Classes

La classe Vehicule est la classe mère (immatriculation, marque, tarif journalier). Les classes Voiture et Moto en héritent et redéfinissent le calcul du prix. La classe Client contient l'identifiant, le nom, l'email et le téléphone. La classe Réservation repose sur un client et un véhicule sur une période. La classe Agence gère les listes, applique les règles et s'occupe de la sauvegarde et du chargement du JSON.

Sauvegarde JSON

Au démarrage, le fichier est lu et chaque véhicule est recréé dans sa bonne classe (Voiture ou Moto) grâce au champ type. Après chaque action, le fichier est réécrit.

Si le fichier n'existe pas (premier lancement), l'agence démarre vide. S'il est invalide, un message est affiché, le fichier n'est pas modifié et le programme s'arrête.

Le compteur prochain_id est sauvegardé, ce qui évite les doublons d'identifiants après un rétablissement.

Rapport

Le détail des classes, le diagramme des relations et l'explication du JSON se trouvent dans le fichier rapport 
