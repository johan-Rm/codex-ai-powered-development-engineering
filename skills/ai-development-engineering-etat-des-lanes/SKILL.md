---
name: ai-development-engineering-etat-des-lanes
description: "Lire l’état des branches et worktrees AIDE sans choisir ni démarrer de tâche."
---

# ai-development-engineering-etat-des-lanes

Avant toute autre lecture liée à la mission, lire le chapitre « Règles de rédaction des réponses et des documents » du `AGENTS.md` applicable.
Appliquer les règles de tests lourds du chapitre « Contrôles qualité et conditions de clôture du travail » d’AGENTS.md.

## Conventions du projet

Lire les instructions du projet, la demande ou carte fournie et les README applicables.
Résoudre les chemins, demandes et branches depuis le projet ; annoncer les valeurs utilisées et les inconnues.
Préserver les modifications préexistantes et les `.env`. Ne pas utiliser stash, reset --hard,
force-push ou suppression de worktree pour résoudre une situation. Ne pas rebaser une branche occupée.
Commit, push, PR et merge nécessitent l’autorisation prévue par le projet ; une invocation d’étape
ne les autorise pas implicitement. Les autorisations explicites déjà données restent valables.
Ne pas déléguer sans autorisation. Ne pas enchaîner automatiquement une autre étape.

## Procédure

Entrée : dépôt et demandes ou périmètres à examiner, ou tous les worktrees enregistrés.
Découvrir les conventions et git worktree list. Pour chaque worktree, relever branche, chemin absolu,
HEAD, modifications suivies et non suivies, écarts avec l’intégration locale et upstream connu.
Examiner les demandes, missions et cartes pertinentes pour distinguer disponibilité et propreté Git.
Ne pas déduire qu’une tâche est libre d’un identifiant de session absent ou d’un arbre propre.
Distinguer en cours, changements à livrer, repos confirmé et disponibilité inconnue.
Sortie et preuve : tableau daté des faits Git, missions et incertitudes ; les références locales
ne garantissent pas l’état distant. Aucun fetch implicite, switch, écriture ou sélection de travail.
Arrêt : inventaire terminé ; signaler les chemins inaccessibles plutôt que les considérer libres.
