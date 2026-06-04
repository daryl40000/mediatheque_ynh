# Médiathèque for YunoHost

[![Packaging Format](https://img.shields.io/badge/packaging_format-2.0-blue.svg)](https://doc.yunohost.org/packaging_apps_manifest)
[![Package license](https://img.shields.io/badge/license-GPLv3-blue.svg)](LICENSE)

*[Lire ce readme en français](./README_fr.md)*

> This package installs **Médiathèque** on a [YunoHost](https://yunohost.org) server.  
> It bundles the [Moncine](https://github.com/daryl40000/Mediatheque) PHP app (current engine, evolving toward a full personal media library).

## Overview

**Médiathèque** is a web app to manage a **personal media collection**: movies, wishlist, ratings, TMDB enrichment, CSV import/export, user accounts, households, loans, visitor sharing, evening quiz, printable lists, and large media storage (PDF magazines, etc.).

**Bundled version:** 0.3.0 ([upstream release](https://github.com/daryl40000/mediatheque/releases/tag/0.3.0))

> **Technical note:** upstream still uses `moncine.db` and `MONCINE_*` environment variables. The YunoHost package id is `mediatheque` so it does not conflict with a separate `moncine` package.

## Main features

- Collection & wishlist, stats, evening quiz
- Shared catalog, TMDB / OMDB enrichment
- Accounts, public registration, households, friends & groups
- CSV import/export, SQLite backup (admin)
- Media storage outside `www/` (`MONCINE_MEDIA_PATH`)
- PDF magazines: **poppler-utils** (`pdftotext`, `pdftoppm`, `pdfinfo`) installed by the package

## Warnings

- **Path**: prefer installing at domain root (`/`). Internal links are absolute.
- **First visit**: create the admin on `/premier-compte.php` after install.
- **TMDB**: put your API key in `data/tmdb_api_key.txt` (YunoHost persistent data dir).
- **E-mail**: password reset and registration need a working mail server (sender `mediatheque@your-domain`).
- **Backup**: back up `moncine.db` before each upgrade.

## Install

```bash
sudo yunohost app install https://github.com/YOUR_ACCOUNT/mediatheque_ynh --debug
```

Then open `https://your-domain/premier-compte.php`.

## Links

- Upstream app: <https://github.com/daryl40000/Moncine>
- YunoHost packaging docs: <https://yunohost.org/packaging_apps>

## Package development

```bash
sudo yunohost app install /path/to/mediatheque_ynh --debug
sudo yunohost app upgrade mediatheque -u /path/to/mediatheque_ynh --debug
```
