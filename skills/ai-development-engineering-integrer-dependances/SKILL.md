---
name: ai-development-engineering-integrer-dependances
description: Intégrer les seuls commits nécessaires à une dépendance AIDE dans une couche affectée et disponible.
---

# Intégrer les commits d’une dépendance

Respecter les instructions et autorisations du projet et de l’étape appelante ; ce skill n’autorise pas d’opération Git supplémentaire. Identifier la carte consommatrice, les commits nécessaires et leur provenance. Vérifier leur contenu, leur ordre et leur présence éventuelle dans la couche destinataire avant toute intégration.

Vérifier le chemin absolu, la branche, l’index, `git status --porcelain=v1 --untracked-files=all` et les missions actives. La couche destinataire doit être affectée, libre et propre ; un arbre propre seul ne prouve pas sa disponibilité. Si elle porte du travail de la même demande, attendre que ses tâches terminées soient isolées et commitées avant toute intégration. Une couche occupée ou sale reste intacte ; signaler le blocage et poursuivre les tâches indépendantes.

Intégrer uniquement les commits identifiés et autorisés. Utiliser une avance rapide si elle ne comprend que les contributions nécessaires ; sinon appliquer un cherry-pick ciblé en conservant la provenance. Ne pas intégrer une branche entière sans en vérifier le contenu, copier des changements non commités, déplacer une mission ou réécrire une branche partagée. Préserver les données, `.env` et worktrees ; aucun stash, reset destructif ou force-push.

Vérifier le résultat et consigner la correspondance entre commits sources et obtenus, ainsi que les conflits et limites. Un conflit qui modifierait un résultat déjà validé nécessite une décision humaine ; ne pas inventer de validation. Restituer la branche et les SHA réels.
