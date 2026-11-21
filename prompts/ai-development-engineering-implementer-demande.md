---
description: "Implémenter toutes les cartes d’une demande, créer un commit local par tâche, puis présenter la demande complète à la vérification humaine."
---

# Développement · 03 Implémentation

Avant toute autre lecture liée à la mission, lire le chapitre « Règles de rédaction des réponses et des documents » du `AGENTS.md` applicable.
Appliquer les règles de tests lourds du chapitre « Contrôles qualité et conditions de clôture du travail » d’AGENTS.md.

## Entrée

Demande cadrée et découpée, cartes identifiées, branches et worktrees affectés.
Une demande entière confie toutes ses cartes ; une carte seule limite le périmètre.

## Conventions du projet

Lire les instructions du projet, la demande, ses cartes et les README applicables.
Les instructions explicites de l’utilisateur priment. Résoudre les chemins, couches,
branches et commandes depuis le projet ; annoncer les worktrees absolus utilisés.
Préserver les modifications étrangères, les données et les `.env`. Aucun stash,
reset --hard, force-push ou rebase de branche occupée. Ne pas déléguer sans autorisation.

L’invocation autorise un commit local distinct par tâche terminée, comprenant code,
tests, documentation et preuves, avant vérification humaine. Un commit technique ne
vaut jamais validation humaine. Ne pas pousser, ouvrir de PR, fusionner ni contribuer
sur intégration ou production. Ne pas enchaîner automatiquement l’étape suivante.

## Vérification de la couche avant démarrage

Avant toute écriture, vérifier le chemin absolu, la branche, l’index et
`git status --porcelain=v1 --untracked-files=all`, ainsi que les missions actives.
Une couche sale ou occupée par une autre mission bloque le démarrage ; ne pas
nettoyer ou committer un travail étranger pour la rendre artificiellement disponible.
Une reprise conserve les seuls changements identifiés de sa mission, y compris ses
cartes préparées à l’analyse. Un arbre propre ne prouve pas la disponibilité.

## Procédure

Dans AIDE, lire le brouillon `tmp/demande-<sujet>.md` du dépôt principal.
Les cartes restent dans `dev-book/tasks/` de leur couche ; ne pas copier le brouillon,
créer la demande définitive ou une branche demands/* à cette étape.

Lire toutes les cartes confiées et déterminer l’ordre des dépendances réelles.
Distinguer dépendances de réalisation et contrôles d’ensemble ; corriger les
prérequis trop larges dans les cartes et la matrice.

Dans une même session conduite par le même agent, réaliser la tâche amont, exécuter
ses contrôles réalisables par l’agent, créer son commit local, puis poursuivre les tâches dépendantes sans
attendre de validation humaine intermédiaire. Une tâche correspond à un commit
initial ; ne pas regrouper plusieurs tâches dans le même commit. Ne pas inventer
une attente entre deux tâches que cette session peut traiter successivement.

Entre sessions ou agents, une dépendance de réalisation bloque son consommateur tant que le commit amont identifié n’est pas disponible. Pour intégrer les commits nécessaires dans une couche affectée, appliquer le skill `ai-development-engineering-integrer-dependances` selon les autorisations du projet. Les contrôles d’ensemble peuvent attendre la réunion des commits sans bloquer les changements indépendants.

Réaliser le périmètre confié avec ses tests et sa documentation. Ne pas modifier
les conventions, Codebase Integrity, seuils ou exceptions pour faire passer un contrôle.
Lorsque la tâche affecte `docs/`, appliquer le skill `ai-development-engineering-documenter-projet` pour préparer un brouillon versionné dans le commit de la tâche ; l’intégration dans `docs/` intervient à la reconstitution.
Faire réaliser les contrôles proportionnés selon la règle commune ; consigner les
commandes, observations et limites dans la carte. Pour préparer et créer chaque commit
autorisé, appliquer le skill `ai-development-engineering-commit`.

Une tâche terminée devient « implémentée et commitée, à vérifier », avec le SHA réel
relevé dans le récapitulatif du brouillon. Ne jamais inscrire « validée » sur la seule
base des tests. Ne pas ajouter un second commit uniquement pour inscrire son propre
SHA dans la carte ; le brouillon permet cette traçabilité sans boucle documentaire.
Une correction ultérieure produit un commit correctif ciblé, sans amend ni réécriture
de l’historique partagé, et reste à vérifier.

Poursuivre toutes les tâches réalisables de la demande. Présenter à l’humain la demande
complète après implémentation, avec couverture des critères, commits, preuves et limites.
La vérification humaine porte alors sur la demande complète, sauf périmètre explicitement
limité par l’humain. Une tâche réellement bloquée doit être signalée ; ne pas annoncer
la demande entièrement implémentée si des travaux requis restent à faire.

## Sortie et preuve

Un commit initial par tâche, tests, documentation, preuves et matrice à jour.
Restitution de la demande complète prête pour vérification humaine, avec les SHA
réels et les éventuels blocages ; aucun verdict humain supposé.

## Arrêt

Travail étranger, couche occupée, dépendance intersession sans commit disponible,
échec de contrôle, besoin de changement du cadre ou dépassement de périmètre :
préserver le travail, signaler le blocage réel et poursuivre les autres tâches indépendantes.
