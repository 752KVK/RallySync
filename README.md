# 752 HOME

Le site du serveur 752 sur Kingshot : https://752kvk.github.io/752Home/

**Outil non officiel fait par des fans. Il n'a aucun lien avec Kingshot ni avec son éditeur.** Il n'utilise aucune image, aucun logo et aucune ressource du jeu.

## Ce qu'il y a dedans
- **Porte du casino** (code 752) à l'entrée.
- **👑 752 ADMIN** (un seul code, retenu 30 jours sur l'appareil) :
  - **RallySync** : calcul du moment de lancement des rallyes, sessions partagées en direct ;
  - **KvK PLAN** : la carte du château, reliée au Battle Roster ;
  - **Battle Roster** : joueurs, alliances, TG, T11, disponibilités.
- **🎲 FUN** (tout le serveur) : mini-jeux, classement de la semaine, tchat.

## Sauvegardes
Dans **752 ADMIN**, le bouton **💾 Sauvegardes** permet de :
- télécharger une sauvegarde complète (sessions RallySync, cartes KvK PLAN, joueurs Battle Roster) ;
- remettre une sauvegarde depuis un fichier, en choisissant les parties à remettre (l'état actuel est d'abord téléchargé par sécurité) ;
- remettre une des copies automatiques : chaque appareil de leader garde une copie par jour des 7 derniers jours.

## Fichiers
- `index.html` : l'accueil, RallySync et KvK PLAN
- `roster.html` : Battle Roster
- `fun.html`, `fun.webmanifest`, `fun-icon-*.png`, `words-*.json` : FUN
- `database.rules.json` : les règles de sécurité Firebase (à coller dans la console Firebase, onglet Règles)

## Sécurité
- Les données des leaders sont rangées dans la base à une adresse secrète tirée du code 752 ADMIN. Le code n'est écrit nulle part dans le site.
- Sans le code, la base refuse toute lecture et toute modification de ces données.
- La configuration Firebase visible dans le code n'est pas un secret : ce sont les règles qui protègent la base.
