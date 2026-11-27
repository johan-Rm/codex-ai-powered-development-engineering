---
name: ai-development-engineering-implementer-demande
description: "Implémenter toutes les cartes d’une demande, créer un commit local par tâche, puis présenter la demande complète à la vérification humaine."
---

# Développement · 03 Implémentation

## Consignes impératives

Avant toute autre lecture liée à la mission, **lire impérativement les fichiers `AGENTS.md` applicables**, globaux et du projet, et respecter leurs consignes.

Consulter également la **documentation pertinente du dossier `docs/`** du projet concerné.

Prêter une attention particulière à la **qualité des réponses** et aux règles encadrant les **exécutions lourdes**, notamment les tests.

**Ne jamais écrire ni modifier de code dans Codebase Integrity pendant l’implémentation d’une demande de développement.** Toute évolution de ce cadre relève d’une demande de consolidation.

## Entrée

Fournir le **numéro de demande `DEM-*`**. Vérifier que la demande existe, que son type est **développement** et qu’elle est cadrée et découpée, avec ses cartes et worktree unique de demande. Si le type ne correspond pas ou ne peut pas être établi, arrêter et signaler le problème.

Par défaut, implémenter **toutes les tâches de la demande**, avec un commit local par tâche terminée au fur et à mesure. Une instruction explicite peut limiter le périmètre à certaines cartes.

Si le worktree de la demande est occupé par une autre mission, préserver son travail et signaler le blocage.

## Contexte et conventions du projet

Lire les instructions du projet, la demande et ses cartes. Dans l’architecture du projet, les README présents à la racine et dans les sous-dossiers, notamment sous `webapp/base/**/*`, définissent les **rôles, responsabilités et conventions techniques** de leurs périmètres. Lire ceux qui existent de la racine jusqu’aux dossiers concernés, sans parcourir les autres dossiers.

Les instructions explicites de l’utilisateur priment. Résoudre les chemins, couches, branches et commandes depuis le projet ; annoncer le worktree absolu de la demande.

Préserver les modifications étrangères, les données et les `.env`. Aucun stash, reset --hard, force-push ou rebase de branche occupée. **Ne pas déléguer sans autorisation.**

L’invocation autorise un commit local distinct par tâche terminée, comprenant code, tests, documentation et preuves, sans validation humaine intermédiaire. Un commit technique ne vaut jamais validation humaine.

Ne pas pousser, ouvrir de PR, fusionner ni contribuer sur intégration ou production. Ne pas enchaîner automatiquement l’étape suivante.

## Vérification du worktree avant démarrage

Avant toute écriture, vérifier le chemin absolu, la branche, l’index et `git status --porcelain=v1 --untracked-files=all`, ainsi que les missions actives.

**Un worktree occupé ou portant du travail étranger bloque le démarrage** ; ne pas nettoyer ou committer ce travail pour le rendre artificiellement disponible. Une reprise conserve les seuls changements identifiés de sa mission, y compris ses cartes préparées à l’analyse.

**Un arbre propre ne prouve pas la disponibilité**.

## Procédure

Lire la demande et les cartes préparées dans le worktree unique de la demande. Conserver leur traçabilité et leur type de couche.

Lire toutes les cartes confiées et déterminer l’ordre des dépendances réelles. Distinguer dépendances de réalisation et contrôles d’ensemble ; corriger les prérequis trop larges dans les cartes et la matrice.

Pour chaque tâche, réaliser les changements, exécuter les contrôles réalisables et créer son commit local. Poursuivre les tâches dépendantes sans attendre de validation humaine intermédiaire.

Une tâche correspond à un commit initial ; ne pas regrouper plusieurs tâches dans le même commit. Inclure la demande et les cartes préparées à l’analyse dans le premier commit de tâche, en identifiant précisément ces changements documentaires.

Entre sessions ou agents, une dépendance de réalisation bloque son consommateur tant que le commit amont identifié n’est pas disponible.

Les dépendances entre tâches sont satisfaites par les commits présents sur la branche unique de la demande. Ne pas copier de travail non commité.

Réaliser le périmètre confié avec ses tests et sa documentation. Ne pas modifier les conventions, seuils ou exceptions pour faire passer un contrôle.

Lorsque la tâche affecte `docs/`, appliquer le skill `ai-development-engineering-documenter-projet` et soumettre les modifications documentaires à la vérification humaine avec la tâche.

Faire réaliser les contrôles proportionnés selon la règle commune ; consigner les commandes, observations et limites dans la carte. Pour préparer et créer chaque commit autorisé, appliquer le skill `ai-development-engineering-commit`.

Une tâche terminée devient « implémentée et commitée, à vérifier » ; relever le SHA réel et les preuves. Ne jamais inscrire « validée » sur la seule base des tests.

Ne pas ajouter un second commit uniquement pour inscrire son propre SHA dans la carte ; la trace de la demande permet cette traçabilité sans boucle documentaire.

Une correction demandée après vérification produit un commit correctif ciblé, sans amend ni réécriture de l’historique partagé ; elle reste à vérifier.

Poursuivre les tâches réalisables puis présenter la demande complète à l’humain : pour chaque tâche, son objectif, le comportement obtenu, les SHA, les preuves, les limites et les éventuels écarts de périmètre ou de code. La vérification humaine porte sur la réalisation des tâches et l’absence de dérive excessive. Ne déduire aucune validation des tests ou du silence.

Une tâche réellement bloquée doit être signalée ; ne pas annoncer la demande entièrement implémentée si des travaux requis restent à faire.

## Sortie et preuve

**Résultat attendu :** Un commit initial par tâche, tests, documentation, preuves et matrice à jour. Restitution de la demande complète prête pour vérification humaine, avec les SHA réels et les éventuels blocages ; aucun verdict humain supposé.

## Arrêt

**Situation bloquante :** Travail étranger, worktree occupé, dépendance intersession sans commit disponible, échec de contrôle, besoin de changement du cadre ou dépassement de périmètre : préserver le travail, signaler le blocage réel et poursuivre les tâches indépendantes réalisables.

## Prochaine étape

Une fois l’implémentation prête, l’étape **04 Vérification / arbitrage** permet à l’humain d’examiner la demande et de donner son verdict. Utiliser le skill `ai-development-engineering-verifier-arbitrer-demande` sur instruction explicite, sans l’enchaîner automatiquement.
