# Rally Sync

Coordinateur de lancement de rallyes pour le jeu mobile Kingshot. Il calcule à quel moment chaque joueur doit lancer son rallye pour que toutes les troupes arrivent au château à la même seconde.

**Outil non officiel fait par des fans. Il n'a aucun lien avec Kingshot ni avec son éditeur, qui ne l'approuvent pas.** Il n'utilise aucune image, aucun logo et aucune ressource du jeu. Kingshot est une marque de son propriétaire.

## Fonctionnalités
- Écran d'entrée « machine à sous » protégé par mot de passe
- **Sessions nommées** (ex. « Castle 11/07 ») : chaque groupe peut travailler sur sa propre session en même temps
- **Partage en direct** : une modification faite sur un appareil apparaît chez tous ceux qui sont dans la même session, et tout reste enregistré après la fermeture du site
- Lien direct vers une session (🔗) et nombre de personnes connectées
- Équipes avec temps de rallye (1, 3, 5, 10 min ou durée personnalisée) et temps de marche de chaque joueur
- Calcul automatique de l'ordre et du moment de lancement, planification à une heure UTC précise
- Décomptes synchronisés sur l'horloge du serveur, avec bips et vibrations à partir de 5 s
- Déplacement des joueurs par glisser-déposer, avec le bouton ⇄ ou au clavier
- Blocs déplaçables, redimensionnables et alignables
- Nom d'alliance et couleurs par alliance ou par bloc
- Interface en anglais, français, coréen et turc, thème clair ou sombre
- Utilisable sur ordinateur et sur téléphone

## Fichiers
- `index.html` : le site complet
- `database.rules.json` : les règles de sécurité à coller dans Firebase (voir plus bas)
- `README.md` : ce fichier

## Mise en ligne (GitHub Pages)
1. Ajoute les fichiers à la racine d'un dépôt **public**.
2. Va dans *Settings → Pages → Deploy from a branch*, puis choisis `main` et `/ (root)`.
3. Le site est disponible à l'adresse `https://<ton-pseudo>.github.io/<nom-du-dépôt>/`.

## Partage en ligne (Firebase Realtime Database, gratuit)
Sans configuration, le site fonctionne en **mode local** : les sessions restent sur l'appareil.
Pour partager les sessions entre tous les appareils :
1. Crée un projet sur <https://console.firebase.google.com> (offre gratuite « Spark », aucune carte bancaire).
2. Crée une **Realtime Database**, puis colle le contenu de `database.rules.json` dans l'onglet *Règles* et publie.
3. Ajoute une **application Web** au projet et copie l'objet `firebaseConfig`.
4. Dans `index.html`, remplace `const FIREBASE_CONFIG = null;` par ta configuration.

La configuration Firebase d'une application Web n'est pas un secret : elle est faite pour être visible dans le code d'un site. Ce qui protège la base, ce sont les règles, qui limitent l'accès au seul dossier de l'application.

## Confidentialité et limites
- Pas de compte, pas de cookie, pas d'outil de suivi.
- **Mode en ligne** : les sessions (noms des joueurs, temps de marche, équipes) sont stockées dans la base Firebase de l'alliance.
- **Mode local** : les sessions sont stockées dans le navigateur.
- Les réglages personnels (langue, thème, volume, position des blocs) restent toujours dans le navigateur de chacun.
- Le mot de passe d'entrée est vérifié dans le navigateur : il éloigne les curieux, mais ce n'est pas une sécurité forte. Toute personne qui a le lien du site et contourne cet écran peut lire et modifier les sessions. N'y mets donc rien de sensible.
