---
name: ai-development-engineering-implementer-consolidation
description: "Réaliser toutes les cartes d’une consolidation, créer un commit local par tâche et présenter la demande complète à la vérification humaine."
---

# Consolidation · 03 Implémentation

## Consignes impératives

Avant toute autre lecture liée à la mission, **lire impérativement les fichiers `AGENTS.md` applicables**, globaux et du projet, et respecter leurs consignes.

Consulter également la **documentation pertinente du dossier `docs/`** du projet concerné.

Prêter une attention particulière à la **qualité des réponses** et aux règles encadrant les **exécutions lourdes**, notamment les tests.

## Entrée

Fournir le **numéro de demande `DEM-*`**. Vérifier que la demande existe, que son type est **consolidation** et qu’elle est analysée et découpée, avec ses décisions de règle confirmées, cartes et worktree unique de demande. Si le type ne correspond pas ou ne peut pas être établi, arrêter et signaler le problème.

Par défaut, implémenter **toutes les tâches de la demande**, avec un commit local par tâche terminée au fur et à mesure. Une instruction explicite peut limiter le périmètre à certaines cartes.

Si le worktree de la demande est occupé par une autre mission, préserver son travail et signaler le blocage.

## Contexte et conventions du projet

Lire les instructions du projet, la demande et ses cartes. Dans l’architecture du projet, les README présents à la racine et dans les sous-dossiers, notamment sous `webapp/base/**/*`, définissent les **rôles, responsabilités et conventions techniques** de leurs périmètres. Lire ceux qui existent de la racine jusqu’aux dossiers concernés, sans parcourir les autres dossiers.

Les instructions explicites de l’utilisateur priment. Résoudre les chemins, couches, branches et commandes depuis le projet ; annoncer le worktree absolu de la demande.

Préserver les modifications étrangères, les données et les `.env`. Aucun stash, reset --hard, force-push ou rebase de branche occupée. **Ne pas déléguer sans autorisation.**

L’invocation autorise un commit local distinct par tâche terminée, comprenant code, tests, documentation et preuves, après validation humaine explicite du changement correspondant. Un commit technique ne vaut jamais validation humaine.

Ne pas pousser, ouvrir de PR, fusionner ni contribuer sur intégration ou production. Ne pas enchaîner automatiquement l’étape suivante.

## Vérification du worktree avant démarrage

Avant toute écriture, vérifier le chemin absolu, la branche, l’index et `git status --porcelain=v1 --untracked-files=all`, ainsi que les missions actives.

**Un worktree occupé ou portant du travail étranger bloque le démarrage** ; ne pas nettoyer ou committer ce travail pour le rendre artificiellement disponible. Une reprise conserve les seuls changements identifiés de sa mission, y compris ses cartes préparées à l’analyse.

**Un arbre propre ne prouve pas la disponibilité**.

## Procédure

Lire la demande et les cartes préparées dans le worktree unique de la demande. Conserver leur traçabilité et leur type de couche.

Lire toutes les cartes confiées et déterminer l’ordre des dépendances réelles. Distinguer dépendances de réalisation et contrôles d’ensemble ; corriger les prérequis trop larges dans les cartes et la matrice.

Pour chaque tâche, réaliser les changements, exécuter les contrôles réalisables, présenter le diff, le comportement, les contrôles et leurs limites, puis attendre une validation humaine explicite avant de créer le commit local. Vérifier que le contenu à committer correspond au contenu validé ; toute modification pertinente impose une nouvelle validation.

Une tâche correspond à un commit initial ; ne pas regrouper plusieurs tâches dans le même commit. Inclure la demande et les cartes préparées à l’analyse dans le premier commit de tâche, en identifiant précisément ces changements documentaires. Avant chaque commit de tâche ou correctif, suspendre l’implémentation, y compris des tâches indépendantes, jusqu’au verdict explicite de l’humain.

Entre sessions ou agents, une dépendance de réalisation bloque son consommateur tant que le commit amont identifié n’est pas disponible.

Les dépendances entre tâches sont satisfaites par les commits présents sur la branche unique de la demande. Ne pas copier de travail non commité.

Réaliser le périmètre confié avec ses corrections, contrôles, tests et documentation. Ne pas modifier une convention, un seuil ou une exception au-delà des arbitrages confirmés à l’étape 02 pour faire passer un contrôle.

Documenter les règles au README responsable et tester les contrôles sur cas conformes, écarts et exceptions ; une décision de règle manquante retourne à l’étape 02.

Lorsque la tâche affecte `docs/`, appliquer le skill `ai-development-engineering-documenter-projet` et soumettre les modifications documentaires à la vérification humaine avec la tâche.

Faire réaliser les contrôles proportionnés selon la règle commune ; consigner les commandes, observations et limites dans la carte. Pour préparer et créer chaque commit autorisé, appliquer le skill `ai-development-engineering-commit`.

Une tâche prête à vérifier reste non commitée. Présenter précisément le diff et les preuves, puis demander un verdict explicite dans le chat. Le silence et les tests ne valent pas validation. Après validation, vérifier le contenu puis créer le commit autorisé et relever son SHA réel. La validation porte sur le contenu présenté, pas sur le reste de la demande.

Ne pas ajouter un second commit uniquement pour inscrire son propre SHA dans la carte ; la trace de la demande permet cette traçabilité sans boucle documentaire.

Si l’humain demande une correction, modifier le changement et le présenter à nouveau avant tout commit. Pour une correction après un commit existant, préparer un correctif ciblé et obtenir sa validation avant un nouveau commit, sans amend ni réécriture de l’historique partagé. Un refus ou report bloque la suite.

Tracer le verdict et sa portée dans les documents de la demande ; après création du commit, relever son SHA sans créer de commit uniquement pour inscrire son propre SHA. Poursuivre ensuite les tâches de la demande. Présenter à l’humain la demande complète après implémentation, avec couverture des critères, commits, preuves et limites.

Après validation de chaque tâche, la vérification humaine finale porte sur la demande complète, sauf périmètre explicitement limité par l’humain. Une tâche réellement bloquée doit être signalée ; ne pas annoncer la demande entièrement implémentée si des travaux requis restent à faire.

## Sortie et preuve

**Résultat attendu :** Un commit initial par tâche, tests, documentation, preuves et matrice à jour. Restitution de la demande complète prête pour vérification humaine, avec les SHA réels et les éventuels blocages ; aucun verdict humain supposé.

## Arrêt

**Situation bloquante :** Travail étranger, worktree occupé, dépendance intersession sans commit disponible, échec de contrôle, besoin de changement du cadre ou dépassement de périmètre : préserver le travail et signaler le blocage réel. Aucun travail sur une autre tâche avant validation du changement présenté et création de son commit.

## Prochaine étape

Une fois l’implémentation prête, l’étape **04 Vérification / arbitrage** permet à l’humain d’examiner la consolidation et de donner son verdict. Utiliser le skill `ai-development-engineering-verifier-arbitrer-consolidation` sur instruction explicite, sans l’enchaîner automatiquement.
