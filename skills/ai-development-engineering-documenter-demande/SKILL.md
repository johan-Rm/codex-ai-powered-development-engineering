---
name: ai-development-engineering-documenter-demande
description: Documenter un cadrage AIDE confirmé en préservant l’identité et les décisions de la demande.
---

# Documenter une demande cadrée

Après confirmation humaine, appliquer les conventions de typage, routage et reprise du projet, notamment `dev-book/README.md#types-de-demandes` lorsqu’il existe. Lire les instructions et README applicables, identifier l’emplacement autorisé et préserver les documents existants. Rechercher une demande ou un brouillon existant avant d’en créer un autre ; conserver son identité et les décisions déjà prises.

Dans AIDE, utiliser `tmp/demande-<sujet>.md` à la racine du dépôt principal, hors worktrees de couche. Vérifier que `tmp/` est ignoré ; si nécessaire, ajouter `/tmp/` dans `.git/info/exclude`, sans modifier les fichiers suivis de develop. Pour une nouvelle demande, examiner les identifiants DEM des références Git locales, des brouillons et des worktrees concernés, sans fetch ; attribuer et réserver le numéro suivant le plus grand observé, sur au moins trois chiffres. Résoudre les collisions avant écriture. La demande définitive est créée à la reconstitution sur la branche dédiée.

Documenter le constat ou besoin, le contexte, le résultat attendu, les contraintes, les critères et les questions ouvertes selon l’étape appelante. Renseigner l’identifiant réel de la session de création depuis le contexte ou une source locale fiable ; en cas d’absence ou de contradiction, signaler le blocage sans l’inventer. Une reprise conserve la session d’origine et ajoute la session intervenante.

Ne pas créer de cartes, de branches ou modifier les conventions et contrôles pendant l’interview, sauf instruction explicite. Restituer le chemin du document et les limites restantes.
