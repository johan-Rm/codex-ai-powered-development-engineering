---
name: ai-development-engineering-preparer-cartes
description: Préparer les cartes et dépendances d’une demande AIDE analysée, selon les couches et conventions du projet.
---

# Préparer les cartes d’une demande

Lire les consignes et conventions applicables, la demande et ses décisions confirmées. Répartir toutes les tâches selon le routage du projet, sans inventer de couche. Avant toute écriture, vérifier le worktree absolu, la branche, l’index, les fichiers non suivis et la disponibilité de la couche. Préserver le travail existant.

Dans AIDE, lire et actualiser la matrice du brouillon `tmp/demande-<sujet>.md` depuis la racine du dépôt principal, sans le copier dans un worktree. Les cartes sont versionnées dans `dev-book/tasks/` de leur couche ; chacune identifie le brouillon par son chemin relatif au principal et prévoit le lien vers la demande définitive sans la présenter comme existante.

Pour chaque carte, fixer l’objectif, les exclusions, les chemins autorisés, les critères, les tests proportionnés, la documentation, les preuves, la branche et le worktree relatif ; annoncer le chemin absolu résolu. Vérifier la couverture de toute la demande. Distinguer les dépendances de réalisation, appuyées sur des commits identifiés, des contrôles d’ensemble qui peuvent attendre la réunion des commits. Ne pas inventer de dépendance de code pour une édition documentaire partagée.

Attribuer les identifiants à partir des références Git locales et des fichiers des worktrees concernés, sans fetch implicite. Renseigner la session réelle de création depuis le contexte ou une source locale fiable ; une absence ou contradiction bloque la création. Une reprise conserve la session d’origine et ajoute celle de l’intervenant. Ne jamais inventer d’identifiant.

Prévoir `demands/<identifiant>` dans le dépôt principal, créée à la reconstitution depuis `develop` local vérifié, et le retour du principal sur `develop` après fusion. Les couches conservent leurs branches `layers/*` ; la branche de demande reste distincte de l’intégration et de la production. Si le principal est occupé, signaler l’attente sans déplacer sa mission. Ne créer ni branche de demande ni copie de réunion à cette étape.

Préparer les branches des worktrees affectés seulement selon les autorisations du projet et de l’étape appelante, après vérification des missions actives. Conserver les branches existantes sans rebase implicite ; une base locale n’établit pas une synchronisation distante. Une couche sale ou occupée bloque la mission concernée ; préserver le travail et poursuivre les tâches indépendantes. Ne pas implémenter les cartes ni copier de travail non commité.

Restituer les chemins, la matrice, les dépendances, l’état réel des branches et les blocages, sans annoncer prête une mission dont les prérequis manquent.
