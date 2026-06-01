## Chemin d’installation

Installez Médiathèque à la **racine du domaine** (`/`) si possible. L’application utilise des liens absolus (`/connexion.php`, etc.) : une installation en sous-dossier peut ne pas fonctionner correctement.

## Prérequis

- PHP 8.2+ (PHP 8.4 fourni par le paquet)
- Extension SQLite3
- **poppler-utils** (`pdftotext`, `pdftoppm`, `pdfinfo`) pour les magazines PDF (recherche, couverture auto)
- Environ **300 Mo** d’espace disque pour le code et les données de base

## Multi-instance

Plusieurs instances Médiathèque peuvent coexister sur le même serveur (domaines ou chemins différents).
