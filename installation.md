# Installer Entracte sur votre Synology

Entracte s'installe comme une application Synology, depuis le Centre de paquets. Tout se fait dans l'interface DSM, depuis votre navigateur : rien à installer sur votre ordinateur (Windows ou autre).

Comptez un quart d'heure la première fois. Ensuite, les mises à jour arrivent toutes seules.

## Ce qu'il faut

- Un Synology sous **DSM 7** (processeur Intel, AMD ou ARM 64 bits). Le modèle est reconnu automatiquement.
- Vos vidéos dans un ou plusieurs dossiers partagés du NAS.

## 1. Préparer le Centre de paquets (une seule fois)

Dans DSM, ouvrez le **Centre de paquets**, puis **Paramètres** :

1. Onglet **Général**, **Niveau de confiance** : « N'importe quel éditeur ». Entracte n'est pas signé par Synology.
2. Onglet **Mise à jour auto** : cochez l'installation automatique et choisissez **toutes les mises à jour** (et non « importantes uniquement »). C'est ce qui permet au NAS de se mettre à jour tout seul.
3. Onglet **Sources de paquets**, **Ajouter** :
   - Nom : `Entracte`
   - Emplacement, selon le processeur du NAS :
     - Intel ou AMD (la plupart des modèles « + » : DS220+, DS920+, DS923+…) : `https://xsyfrost.github.io/entracte/dsm/x86_64.json`
     - ARM 64 bits (DS220j, DS223, DS118…) : `https://xsyfrost.github.io/entracte/dsm/armv8.json`

   En cas de doute : **Panneau de configuration**, **Centre d'infos** : le processeur y est indiqué.

## 2. Installer

1. Dans le Centre de paquets, onglet **Communauté** (à gauche) : Entracte y apparaît. Cliquez sur **Installer**.
2. Acceptez l'avertissement « développeurs tiers ».
3. L'écran **Accès à vos vidéos** annonce ce que DSM va faire : donner à Entracte, et à lui seul, la lecture et l'écriture sur vos dossiers partagés (la liste est affichée ; vos dossiers personnels « homes » restent fermés). La lecture sert à trouver vos films et séries, l'écriture uniquement à ranger ce que la synchronisation rapatrie. Rien à régler dans les Autorisations : cliquez sur **Suivant**, puis **Terminé**.
4. Ouvrez le **menu principal** de DSM : l'icône Entracte y est. DSM ne place jamais une application sur le bureau tout seul : faites glisser l'icône du menu jusqu'au bureau.

DSM donne lui-même à Entracte l'accès à la puce vidéo du NAS, s'il en a une.

Sans la source (installation à la main) : sur https://github.com/xsyfrost/entracte/releases, téléchargez le `.spk` de votre processeur (`x86_64` ou `armv8`), puis **Centre de paquets**, **Installation manuelle**.

## 3. Les mises à jour

Plus rien à faire : à chaque nouvelle version publiée, le NAS l'installe tout seul (en général dans la nuit), les téléphones proposent leur mise à jour à l'ouverture, et les télévisions installées depuis le NAS sont mises à jour sans rien toucher (jamais pendant qu'on regarde).

Dans Entracte, **Réglages**, **Installation**, étape **Mises à jour** : la version installée, la dernière publiée, les fichiers à télécharger (paquet du NAS, application Android) et les trois réglages ci-dessus, cochés en vert dès qu'ils sont faits.

## 4. Premier lancement

Cliquez sur l'icône Entracte.

1. **Bienvenue** : choisissez votre prénom, puis **Commencer**. C'est le profil administrateur. Les autres membres de la maison auront chacun le leur, sans mot de passe à la maison.
2. **Configuration**, en trois étapes :
   - **Recherche de vos vidéos** : Entracte parcourt vos dossiers partagés (30 secondes au plus ; **Arrêter et choisir moi-même** pour aller plus vite).
   - **Vos catégories** : Films, Séries, Documentaires et Adulte. Vérifiez les dossiers proposés, ou **Choisir le dossier**. Documentaires et Adulte sont facultatives.
     Films et séries dans un même dossier ? Choisissez ce dossier pour **Films** et pour **Séries** : Entracte donne les épisodes (S01E02, dossiers « Saison 1 »…) aux Séries et le reste aux Films.
   - **Affiches, résumés et bandes-annonces** : suivez les étapes pour créer une clé TMDB gratuite. TMDB affiche deux valeurs : collez la **API Key** (la courte, 32 caractères) ; la longue, « API Read Access Token », fonctionne aussi. **Vérifier et enregistrer**, puis **Terminer et lancer l'analyse**.
3. **Préparation de votre bibliothèque** : une barre de progression suit l'analyse des fichiers, la reconnaissance des titres et le téléchargement des affiches. Cela ne se fait qu'une fois (**Afficher sans attendre** pour passer).
4. Ensuite, dans **Réglages** (rond avec votre initiale, en haut à droite) :
   - **Installation**, étape **Applications** : le QR code installe l'application sur les téléphones Android. Pour une Android TV ou une Shield, l'application **Downloader** avec l'adresse affichée, ou **Rechercher ma télévision** pour que le NAS l'installe et la tienne à jour.
   - **Installation**, étape **Mises à jour** : les trois réglages de l'étape 1 doivent être cochés en vert.

Un dossier partagé créé après l'installation peut être signalé « pas le droit de lire » : **Panneau de configuration**, **Dossier partagé**, le dossier concerné, **Modifier**, **Autorisations**. Dans la liste en haut, choisissez **Utilisateur système interne**, puis cochez **Lecture/Écriture** pour **entracte**.

## La catégorie réservée (films pour adultes)

Elle n'apparaît jamais sur l'accueil, dans « Reprendre » ni dans la recherche, et TMDB n'est jamais interrogé pour ses fichiers. Changez son **code à 4 chiffres** (0000 au départ) dans **Réglages**.

Chaque profil choisit, dans **Réglages**, puis **Catégories**, comment la voir :
- **Masquée** : elle n'existe pas pour ce profil.
- **Dans le menu** : avec le code à l'ouverture (profils administrateurs).
- **Discrète** : rien n'apparaît nulle part. Pour la faire apparaître : **5 appuis rapides sur le logo** Entracte (sur la télévision, 5 appuis sur OK quand le logo est sélectionné), ou un appui long sur le logo, ou le code tapé dans la recherche (site web), puis le code. Le code ne vous emmène nulle part : il ajoute seulement l'onglet de la catégorie dans la barre du haut. Pour la refermer, entrez dedans et choisissez **Masquer**. Un mauvais code ne montre rien.

Dans cette catégorie, l'onglet **En ligne** cherche des vidéos sur les plateformes activées dans **Réglages**, **Vidéos en ligne**, toutes à la fois, avec favoris et vidéos déjà vues. Dans l'application, la lecture se fait sans publicité ni fenêtre surgissante.

## La synchronisation : seedbox ou FTP / SFTP

Dans **Réglages**, **Synchronisation**, **Ajouter un serveur**, choisissez le type :

- **Seedbox ruTorrent (conseillé)** : l'adresse de ruTorrent (`https://…/rutorrent/`), puis les identifiants SFTP de la seedbox (ceux de ruTorrent sont souvent les mêmes). Entracte demande à ruTorrent toutes les 15 secondes où en sont les téléchargements : un torrent terminé est rapatrié **aussitôt**. Pour ne prendre que vos torrents sur une seedbox partagée, mettez-leur une **étiquette** dans ruTorrent (par exemple votre prénom) et indiquez-la dans **Étiquettes à prendre** ; le **dossier à surveiller** limite aussi ce qui est pris. Pendant un téléchargement, sa progression s'affiche dans Entracte.
- **Serveur FTP ou SFTP** : Entracte regarde chaque minute (connexion gardée ouverte) et prend un fichier une minute après sa dernière écriture.

Dans les deux cas, Entracte ne fait que lire le serveur (il n'y supprime, n'y renomme et n'y dépose jamais rien), ne rapatrie chaque vidéo qu'une fois, puis la range seule. Dans **Où ranger**, choisissez le dossier des Films, des Séries et des Documentaires. Entracte doit avoir le droit d'écrire dans ces dossiers (voir « pas le droit de lire » plus haut, et cochez Lecture/Écriture).

## En cas de souci

- **Entracte ne démarre pas** : Centre de paquets, Entracte, **Journal**. Envoyez ce qui s'affiche à la personne qui vous a installé Entracte.
- **Pas d'affiches** : vérifiez la clé TMDB dans l'assistant.
- **La vidéo saccade dans le navigateur** : utilisez l'application Android, qui lit tous les formats sans conversion.
