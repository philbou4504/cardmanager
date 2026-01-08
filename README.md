Méthodologie de Conception : Application R.U.S. Biesme
Auteur : Philippe BOUNAMEAU
Date : Janvier 2026
Objectif : Gestion informatisée des sanctions sportives (Cartons Jaunes/Rouges) et des suspensions pour un club de football. EXCLUSIVEMENT POUR SMARTPHONE! PAS PC, PAS TABLETTE
________________________________________
1. Architecture Technique
L'application est conçue comme une Single Page Application (SPA) utilisant les technologies Web standards, permettant une exécution sans serveur (Serverless) et une compatibilité multi-support (iPad, PC, Smartphone).
•	HTML5 : Structure sémantique et interface utilisateur.
•	CSS3 : Design "Dark Mode" optimisé pour la visibilité en extérieur et interface tactile.
•	JavaScript (Vanilla) : Logique métier, calcul des suspensions et gestion des données.
•	LocalStorage : Base de données locale persistante intégrée au navigateur.
2. Logique Métier & Algorithmes
L'application repose sur trois piliers de calcul :
A. Calcul des Statuts (Badge de sécurité)
Le système évalue en temps réel l'état du joueur selon le mode sélectionné :
•	Mode Championnat :
o	OK : 0 ou 1 carte jaune.
o	EN DANGER : 2 cartes jaunes (Alerte orange).
o	SUSPENDU : 3 cartes jaunes ou 1 carte rouge ou suspension manuelle.
•	Mode Coupe :
o	OK : 0 carte jaune.
o	EN DANGER : 1 carte jaune (Alerte orange).
o	SUSPENDU : 2 cartes jaunes ou 1 carte rouge ou suspension manuelle.
B. Gestion de l'Historique (Logs)
Chaque action est enregistrée avec un horodatage (Date.now()). Cela permet :
•	Le retrait précis de la dernière carte encodée par erreur sans affecter le reste du bilan.
•	La traçabilité lors de l'archivage saisonnier.
C. Persistance et Portabilité
Les données sont converties au format JSON pour permettre l'exportation et l'importation. Cette méthode garantit que les données ne sont pas perdues lors d'un changement d'appareil.
3. Fonctionnalités Implémentées
1.	Sélecteur de Catégories : Segmentation de P1/P3 jusqu'à U13.
2.	Gestion des Suspensions Manuelles : Système "À Purger" pour gérer les suspensions administratives de la fédération.
3.	Module d'Archivage : Gel des données en fin de saison et génération d'un rapport annuel de discipline.
4.	Interface Mobile : Boutons de grande taille pour une utilisation "terrain" et prévention des erreurs (confirmations de suppression).
4. Maintenance et Sécurité
•	Sauvegarde : Il est recommandé d'exporter le fichier JSON mensuellement.
•	Vie privée : Aucune donnée n'est envoyée vers un serveur externe ; tout reste sur l'appareil de l'utilisateur.
