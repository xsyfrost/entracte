# Entracte

Serveur multimédia personnel pour Synology (DSM 7), avec applications Android et Android TV : vos films et séries, avec affiches, reprise de lecture et sous-titres, à la maison comme en déplacement.

## Installer

**Le guide d'installation pas à pas : [installation](https://xsyfrost.github.io/entracte/installation)** (aussi lisible ici : [installation.md](installation.md)).

En bref, dans le Centre de paquets de DSM, **Paramètres** :
1. **Général** : niveau de confiance « N'importe quel éditeur ».
2. **Mise à jour auto** : toutes les mises à jour.
3. **Sources de paquet** : ajoutez `https://xsyfrost.github.io/entracte/dsm/x86_64.json` (Intel ou AMD) ou `https://xsyfrost.github.io/entracte/dsm/armv8.json` (ARM 64 bits).

Puis onglet **Communauté** : **Installer**. Les mises à jour arrivent ensuite toutes seules.

Ce dépôt ne contient que les versions publiées (onglet **Releases**), le catalogue du Centre de paquets (`dsm/`) et cette documentation.
