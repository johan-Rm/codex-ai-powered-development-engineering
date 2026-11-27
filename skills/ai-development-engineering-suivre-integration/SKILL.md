---
name: ai-development-engineering-suivre-integration
description: Vérifier une intégration AIDE et suivre l’état local autorisé après fusion.
---

# Suivre une intégration

Respecter les autorisations du projet et de l’étape appelante et lire `/home/johan/.codex/skills/references/git-workflow.md`. Vérifier la fusion distante, son SHA, le message intégré et la correspondance entre le HEAD de PR contrôlé, son diff et le commit intégré ; signaler toute divergence du message. Une équivalence de patch seule ne prouve pas l’intégration.

Vérifier les worktrees, branches, missions, index et fichiers non suivis avant toute action locale. Actualiser `develop` uniquement si son checkout est libre et propre et si l’opération est autorisée ; privilégier l’avance rapide. Préserver les autres demandes, les anciens worktrees de couche, les données et les `.env`. Ne pas utiliser stash, reset destructif, force-push ou suppression de worktree pour résoudre un blocage. Un arbre propre ne prouve pas la disponibilité.

Ne pas supprimer automatiquement le worktree ou la branche de demande ; leur cycle de vie et toute suppression nécessitent une autorisation applicable. Consigner les SHA, l’URL réelle, les contrôles et blocages dans la trace prévue, sans modifier directement les fichiers suivis de `develop`. Restituer l’état observé et ne pas annoncer la clôture si le suivi requis est bloqué. La promotion vers `master` nécessite une demande distincte.
