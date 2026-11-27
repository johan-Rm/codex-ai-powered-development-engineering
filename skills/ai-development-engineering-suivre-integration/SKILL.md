---
name: ai-development-engineering-suivre-integration
description: Vérifier une intégration AIDE et suivre l’état local autorisé après fusion.
---

# Suivre une intégration

Respecter les autorisations du projet et de l’étape appelante et lire `/home/johan/.codex/skills/references/git-workflow.md`. Vérifier la fusion distante, son SHA, le message intégré et la correspondance entre le HEAD de PR contrôlé, son diff et le commit intégré ; signaler toute divergence du message. Une équivalence de patch seule ne prouve pas l’intégration.

Vérifier les worktrees, branches, missions, index et fichiers non suivis avant toute action locale. Actualiser `develop` uniquement si son checkout est libre et propre et si l’opération est autorisée ; privilégier l’avance rapide. Préserver les autres demandes, les anciens worktrees de couche, les données et les `.env`. Ne pas utiliser stash, reset destructif, force-push ou suppression de worktree pour résoudre un blocage. Un arbre propre ne prouve pas la disponibilité.

Consigner les SHA, l’URL réelle, les contrôles et blocages dans la trace prévue, sans modifier directement les fichiers suivis de `develop`. Distinguer l’intégration vérifiée, le suivi local et la clôture des espaces : une demande intégrée peut conserver temporairement son worktree, sa branche et ses ressources. Signaler séparément tout suivi local bloqué et toute clôture différée. La promotion vers `master` nécessite une demande distincte.

Sur demande, inventorier ensemble les demandes fusionnées et leurs espaces conservés : identité, PR et SHA de fusion, worktree et branche, activité connue, ressources et données, vérifications disponibles et blocages. Un état Git propre ne suffit pas à établir l’absence d’activité ou de travail inédit. Une information inconnue reste à vérifier ; ne pas qualifier l’espace de disponible sur cette seule base.

La clôture est une opération distincte, ciblée et explicitement autorisée ; la livraison ne l’autorise pas automatiquement. Avant chaque suppression, vérifier la fusion et le rattachement du travail au squash, l’absence de commits ou modifications inédits, y compris les fichiers non suivis et ignorés, et l’absence d’activité ou de mission en cours. Identifier les données, fichiers locaux et ressources associés, y compris `.env`, services, volumes et caches, ainsi que leur éventuel partage ; préciser ce qui sera préservé ou retiré. Un doute, une activité ou un travail inédit bloque l’élément concerné. Présenter les opérations et les blocages, puis ne supprimer que les éléments ciblés par l’autorisation applicable. Ne pas supprimer les anciens worktrees de couche pendant la transition.
