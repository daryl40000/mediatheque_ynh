# Médiathèque pour YunoHost

[![Packaging Format](https://img.shields.io/badge/packaging_format-2.0-blue.svg)](https://doc.yunohost.org/packaging_apps_manifest)
[![Licence paquet](https://img.shields.io/badge/license-GPLv3-blue.svg)](LICENSE)

*[English readme](./README.md)*

> Ce paquet permet d’installer **Médiathèque** sur un serveur [YunoHost](https://yunohost.org).  
> Il embarque l’application [Moncine](https://github.com/daryl40000/Moncine) (moteur PHP actuel, en évolution vers une médiathèque complète).

## Vue d’ensemble

**Médiathèque** est une application web pour gérer une **collection personnelle de médias** : films, envies, notes, enrichissement TMDB, import/export CSV, comptes utilisateurs, foyers, prêts entre amis, partage visiteur, questionnaire du soir, listes imprimables, stockage de médias volumineux (magazines PDF, etc.).

**Version incluse :** 1.0.5 ([release upstream](https://github.com/daryl40000/Moncine/releases/tag/1.0.5))

> **Note technique :** le code upstream utilise encore les noms `moncine.db` et les variables `MONCINE_*` ; le paquet YunoHost s’identifie comme `mediatheque` pour ne pas entrer en conflit avec un éventuel paquet `moncine`.

## Fonctionnalités principales

- Collection et envies, statistiques, questionnaire du soir
- Catalogue partagé, enrichissement TMDB / OMDB
- Comptes, inscription publique, foyers, amis et groupes
- Import / export CSV, sauvegarde SQLite (admin)
- Stockage médias hors `www/` (`MONCINE_MEDIA_PATH`)
- Magazines PDF : **poppler-utils** (`pdftotext`, `pdftoppm`, `pdfinfo`) installé par le paquet

## Avertissements

- **Chemin** : préférez l’installation à la racine du domaine (`/`). Les liens internes sont absolus.
- **Première visite** : créez l’administrateur sur `/premier-compte.php` après l’installation.
- **TMDB** : placez votre clé dans `data/tmdb_api_key.txt` (dossier persistant YunoHost).
- **E-mails** : mot de passe oublié et inscription nécessitent un serveur mail fonctionnel (expéditeur `mediatheque@votre-domaine`).
- **Sauvegarde** : sauvegardez `moncine.db` avant chaque mise à jour.

## Installation

```bash
sudo yunohost app install https://github.com/VOTRE_COMPTE/mediatheque_ynh --debug
```

Puis ouvrez `https://votre-domaine/premier-compte.php`.

## Liens

- Application upstream : <https://github.com/daryl40000/Moncine>
- Documentation packaging YunoHost : <https://yunohost.org/packaging_apps>

## Développement du paquet

```bash
sudo yunohost app install /chemin/vers/mediatheque_ynh --debug
sudo yunohost app upgrade mediatheque -u /chemin/vers/mediatheque_ynh --debug
```
