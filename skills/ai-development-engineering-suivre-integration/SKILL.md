---
name: ai-development-engineering-suivre-integration
description: Suivre une intégration AIDE vérifiée et réaligner les couches locales disponibles.
---

# Suivre une intégration

Respecter les instructions et autorisations du projet et de l’étape appelante. Consulter la référence commune `/home/johan/.codex/skills/references/git-workflow.md`. Avant toute action, vérifier l’intégration distante de la PR, son SHA et la correspondance des commits. Une équivalence de patch seule ne prouve pas l’intégration.

Inventorier les worktrees, missions, branches, index, fichiers non suivis et divergences. Actualiser `develop` et réaligner uniquement les couches locales confirmées libres, propres et sans travail inédit, conformément au projet. Une couche occupée, sale ou portant du travail inédit reste intacte et bloque la clôture ; un arbre propre ne prouve pas sa disponibilité.

Une avance rapide est privilégiée. Un rebase local sans commit à rejouer est permis uniquement lorsque le projet l’autorise explicitement, après preuve d’intégration et correspondance de toutes les contributions ; jamais sur une branche partagée ou occupée. Ne pas utiliser reset destructif, stash, force-push ou suppression de worktree. Préserver les `.env` et les données.

Dans AIDE, revenir sur `develop` dans le principal libre et propre, ne pas publier les branches `layers/*` et vérifier l’égalité des SHA de `develop` et de toutes les couches configurées. Supprimer seulement les branches temporaires livrées, libres, sans autre PR ni travail inédit, après vérification de leur intégration et selon les autorisations du projet ; aucune suppression forcée. Ne jamais supprimer `develop`, `master` ou une branche de couche.

Consigner les SHA, l’URL réelle, les contrôles, l’alignement et les blocages dans la trace existante, sans modifier directement les fichiers suivis de `develop`. Restituer l’état observé ; ne pas annoncer la clôture si une couche reste non alignée et ne pas ouvrir de PR vers `master` sans demande distincte.
