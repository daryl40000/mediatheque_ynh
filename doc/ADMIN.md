## Administration

- **User accounts**: `/utilisateurs.php` (admin)
- **Households** (shared collection): `/foyers.php` (admin)
- **Catalog maintenance** (duplicates, DB backup): `/maintenance-catalogue.php` (admin)
- **Large media storage**: `/maintenance-medias.php` (admin)

## Important paths

| Location | Contents |
|----------|----------|
| `__INSTALL_DIR__/` | PHP code (www/, lib/, templates/, sql/) |
| `__DATA_DIR__/moncine.db` | SQLite database |
| `__DATA_DIR__/tmdb_api_key.txt` | TMDB API key |
| `__DATA_DIR__/posters/` | Local posters |
| `__DATA_DIR__/media/` | Large files (PDF, exports…) |

## Upgrade

Upgrades automatically run SQL migrations via `lib/cli/migrate.php`. Back up `moncine.db` before upgrading.

## Environment variables (PHP-FPM)

Set in `/etc/php/__PHP_VERSION__/fpm/pool.d/__APP__.conf`:

| Variable | Purpose |
|----------|---------|
| `MONCINE_DATA_PATH` | Data directory (`__DATA_DIR__`) |
| `MONCINE_MEDIA_PATH` | Large media root |
| `MONCINE_BASE_URL` | Public URL (e-mails, links) |
| `MONCINE_TRUST_PROXY` | `1` — real client IP behind YunoHost Nginx |
| `MONCINE_MAIL_FROM` | Mail sender (`mediatheque@…`) |

## PDF magazines (Poppler)

The package installs **poppler-utils**: `pdftotext` (first 6 pages text for search), `pdftoppm` (cover), `pdfinfo` (page count).

## Large uploads (PDF magazines)

The package sets **400M** for `upload_max_filesize` / `post_max_size`, **512M** for `memory_limit`, and Nginx `client_max_body_size` to **400M** (the app allows up to **350M** per file).

After upgrading the package, check `/etc/php/*/fpm/pool.d/__APP__.conf` that these values are applied.

Upstream docs: [Moncine on GitHub](https://github.com/daryl40000/Moncine)
