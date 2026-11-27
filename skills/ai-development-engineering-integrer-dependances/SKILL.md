---
name: ai-development-engineering-integrer-dependances
description: Vérifier les commits nécessaires à une dépendance AIDE sur la branche de demande.
---

# Intégrer les commits d’une dépendance

Respecter les instructions et autorisations du projet et de l’étape appelante ; ce skill n’autorise pas d’opération Git supplémentaire. Identifier la carte consommatrice, les commits nécessaires et leur provenance. Vérifier leur contenu, leur ordre et leur présence sur la branche de la demande.

Vérifier le chemin absolu du worktree de la demande, sa branche, son index, `git status --porcelain=v1 --untracked-files=all` et les missions actives. Un worktree occupé par une autre mission ou portant du travail étranger reste intact ; signaler le blocage. Un arbre propre seul ne prouve pas sa disponibilité. Une reprise conserve les seuls changements identifiés de la demande.

Dans le workflow à worktree unique, poursuivre lorsque les commits requis sont présents ; sinon signaler la dépendance manquante. Ne pas effectuer de cherry-pick ou d’autre intégration par défaut. Pour une demande ancienne ou une dépendance externe, toute opération Git exige une autorisation applicable et la vérification de sa provenance et de son périmètre. Ne pas copier des changements non commités, déplacer une mission ou réécrire une branche partagée. Préserver les données, `.env` et worktrees ; aucun stash, reset destructif ou force-push.

Consigner les commits vérifiés et les limites ; en cas d’intégration autorisée, relever les SHA sources et obtenus ainsi que les conflits. Un conflit qui modifierait un résultat déjà validé nécessite une décision humaine ; ne pas inventer de validation. Restituer la branche et les SHA réels.
