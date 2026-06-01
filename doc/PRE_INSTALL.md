## Install path

Install Médiathèque at the **domain root** (`/`) when possible. The app uses absolute URLs (`/connexion.php`, etc.); subfolder installs may not work correctly.

## Requirements

- PHP 8.2+ (PHP 8.4 provided by the package)
- SQLite3 extension
- **poppler-utils** (`pdftotext`, `pdftoppm`, `pdfinfo`) for PDF magazines (search, auto cover)
- About **300 MB** disk space for code and basic data

## Multi-instance

Several Médiathèque instances can run on the same server (different domains or paths).
