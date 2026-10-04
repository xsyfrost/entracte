# Entracte

Serveur multimédia personnel pour Synology (DSM 7), avec applications Android et Android TV.

Ce dépôt ne contient que les versions publiées. Chaque NAS où Entracte est installé lit la dernière version ici et la propose dans son Centre de paquets.

## Installer

1. Téléchargez le paquet de la dernière version (onglet Releases) : `x86_64` pour les Synology à processeur Intel ou AMD, `armv8` pour les ARM 64 bits.
2. DSM, Centre de paquets, Paramètres : niveau de confiance « N'importe quel éditeur ».
3. Centre de paquets, Installation manuelle : choisissez le fichier .spk.
4. Ouvrez Entracte depuis le menu principal de DSM : la configuration guidée fait le reste.

## Mises à jour automatiques

Centre de paquets, Paramètres, Sources de paquets : ajoutez `http://127.0.0.1:8420/dsm`. Puis activez les mises à jour automatiques pour Entracte.
