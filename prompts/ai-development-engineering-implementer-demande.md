---
description: "Implémenter toutes les cartes d’une demande, créer un commit local par tâche, puis présenter la demande complète à la vérification humaine."
---

# Développement · 03 Implémentation

## Consignes impératives

Avant toute autre lecture liée à la mission, **lire impérativement les fichiers `AGENTS.md` applicables**, globaux et du projet, et respecter leurs consignes.

Consulter également la **documentation pertinente du dossier `docs/`** du projet concerné.

Prêter une attention particulière à la **qualité des réponses** et aux règles encadrant les **exécutions lourdes**, notamment les tests.

**Ne jamais écrire ni modifier de code dans Codebase Integrity pendant l’implémentation d’une demande de développement.** Toute évolution de ce cadre relève d’une demande de consolidation.

## Entrée

Fournir le **numéro de demande `DEM-*`**. Vérifier que la demande existe, que son type est **développement** et qu’elle est cadrée et découpée, avec ses cartes, branches et worktrees affectés. Si le type ne correspond pas ou ne peut pas être établi, arrêter et signaler le problème.

Par défaut, implémenter **toutes les tâches de la demande**, avec un commit local par tâche terminée au fur et à mesure. Une instruction explicite peut limiter le périmètre à certaines cartes.

Si une couche est occupée par une autre mission, préserver son travail, signaler les tâches bloquées et poursuivre celles qui restent réalisables indépendamment.

## Contexte et conventions du projet

Lire les instructions du projet, la demande et ses cartes. Dans l’architecture du projet, les README présents à la racine et dans les sous-dossiers, notamment sous `webapp/base/**/*`, définissent les **rôles, responsabilités et conventions techniques** de leurs périmètres. Lire ceux qui existent de la racine jusqu’aux dossiers concernés, sans parcourir les autres dossiers.

Les instructions explicites de l’utilisateur priment. Résoudre les chemins, couches, branches et commandes depuis le projet ; annoncer les worktrees absolus utilisés.

Préserver les modifications étrangères, les données et les `.env`. Aucun stash, reset --hard, force-push ou rebase de branche occupée. **Ne pas déléguer sans autorisation.**

L’invocation autorise un commit local distinct par tâche terminée, comprenant code, tests, documentation et preuves, avant vérification humaine. Un commit technique ne vaut jamais validation humaine.

Ne pas pousser, ouvrir de PR, fusionner ni contribuer sur intégration ou production. Ne pas enchaîner automatiquement l’étape suivante.

## Vérification de la couche avant démarrage

Avant toute écriture, vérifier le chemin absolu, la branche, l’index et `git status --porcelain=v1 --untracked-files=all`, ainsi que les missions actives.

**Une couche sale ou occupée par une autre mission bloque le démarrage** ; ne pas nettoyer ou committer un travail étranger pour la rendre artificiellement disponible. Une reprise conserve les seuls changements identifiés de sa mission, y compris ses cartes préparées à l’analyse.

**Un arbre propre ne prouve pas la disponibilité**.

## Procédure

Dans AIDE, lire le brouillon `tmp/demande-<sujet>.md` du dépôt principal. Les cartes restent dans `dev-book/tasks/` de leur couche ; ne pas copier le brouillon, créer la demande définitive ou une branche demands/* à cette étape.

Lire toutes les cartes confiées et déterminer l’ordre des dépendances réelles. Distinguer dépendances de réalisation et contrôles d’ensemble ; corriger les prérequis trop larges dans les cartes et la matrice.

Dans une même session conduite par le même agent, réaliser la tâche amont, exécuter ses contrôles réalisables par l’agent, créer son commit local, puis poursuivre les tâches dépendantes sans attendre de validation humaine intermédiaire.

Une tâche correspond à un commit initial ; ne pas regrouper plusieurs tâches dans le même commit. Ne pas inventer une attente entre deux tâches que cette session peut traiter successivement.

Entre sessions ou agents, une dépendance de réalisation bloque son consommateur tant que le commit amont identifié n’est pas disponible.

Pour intégrer les commits nécessaires dans une couche affectée, appliquer le skill `ai-development-engineering-integrer-dependances` selon les autorisations du projet. Les contrôles d’ensemble peuvent attendre la réunion des commits sans bloquer les changements indépendants.

Réaliser le périmètre confié avec ses tests et sa documentation. Ne pas modifier les conventions, seuils ou exceptions pour faire passer un contrôle.

Lorsque la tâche affecte `docs/`, appliquer le skill `ai-development-engineering-documenter-projet` pour préparer un brouillon versionné dans le commit de la tâche ; l’intégration dans `docs/` intervient à la reconstitution.

Faire réaliser les contrôles proportionnés selon la règle commune ; consigner les commandes, observations et limites dans la carte. Pour préparer et créer chaque commit autorisé, appliquer le skill `ai-development-engineering-commit`.

Une tâche terminée devient « implémentée et commitée, à vérifier », avec le SHA réel relevé dans le récapitulatif du brouillon. Ne jamais inscrire « validée » sur la seule base des tests.

Ne pas ajouter un second commit uniquement pour inscrire son propre SHA dans la carte ; le brouillon permet cette traçabilité sans boucle documentaire.

Une correction ultérieure produit un commit correctif ciblé, sans amend ni réécriture de l’historique partagé, et reste à vérifier.

Poursuivre toutes les tâches réalisables de la demande. Présenter à l’humain la demande complète après implémentation, avec couverture des critères, commits, preuves et limites.

La vérification humaine porte alors sur la demande complète, sauf périmètre explicitement limité par l’humain. Une tâche réellement bloquée doit être signalée ; ne pas annoncer la demande entièrement implémentée si des travaux requis restent à faire.

## Sortie et preuve

**Résultat attendu :** Un commit initial par tâche, tests, documentation, preuves et matrice à jour. Restitution de la demande complète prête pour vérification humaine, avec les SHA réels et les éventuels blocages ; aucun verdict humain supposé.

## Arrêt

**Situation bloquante :** Travail étranger, couche occupée, dépendance intersession sans commit disponible, échec de contrôle, besoin de changement du cadre ou dépassement de périmètre : préserver le travail, signaler le blocage réel et poursuivre les autres tâches indépendantes.

## Prochaine étape

Une fois l’implémentation prête, l’étape **04 Vérification / arbitrage** permet à l’humain d’examiner la demande et de donner son verdict. Utiliser le prompt `ai-development-engineering-verifier-arbitrer-demande` sur instruction explicite, sans l’enchaîner automatiquement.
