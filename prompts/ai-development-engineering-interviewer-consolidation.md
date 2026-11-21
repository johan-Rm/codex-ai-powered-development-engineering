---
description: "Clarifier un constat de consolidation et documenter une proposition de convention technique à examiner."
---

# Consolidation · 01 Interview

Avant toute autre lecture liée à la mission, lire le chapitre « Règles de rédaction des réponses et des documents » du `AGENTS.md` applicable.
Appliquer les règles de tests lourds du chapitre « Contrôles qualité et conditions de clôture du travail » d’AGENTS.md.

## Entrée

Constat humain direct, revue ou observation disponible ; aucune demande de développement préalable nécessaire.

## Conventions du projet

Lire les instructions du projet, la demande ou carte fournie et les README applicables.
Résoudre les chemins, couches, branches, commandes de tests et qualité depuis le projet ;
annoncer les valeurs utilisées et les inconnues, sans imposer de valeurs personnelles.
Avant une écriture, confirmer le dossier absolu et le périmètre autorisé. Dans AIDE,
le brouillon est écrit dans le tmp ignoré du dépôt principal, sans réserver de couche
ni changer de branche ; aucune écriture suivie directement sur develop ou production.
Préserver les modifications préexistantes et les `.env`. Ne pas utiliser stash, reset --hard,
force-push ou suppression de worktree pour résoudre une situation. Ne pas rebaser une branche occupée.
Commit, push, PR et merge nécessitent l’autorisation prévue par le projet ; une invocation d’étape
ne les autorise pas implicitement. Les autorisations explicites déjà données restent valables.
Ne pas déléguer sans autorisation. Ne pas enchaîner automatiquement une autre étape.

## Procédure

Lire les décisions existantes et distinguer faits, hypothèses, propositions et questions ouvertes. Ne pas redemander une décision déjà prise ni présenter une proposition comme approuvée.

Conduire l’échange avec `request_user_input_async`, ou `request_user_input` si le mode actif l’autorise. Sans outil interactif disponible, signaler la limite et garder l’interview en attente. Poser une question à la fois, avec des choix concrets et une réponse libre lorsque cela aide ; attendre la réponse avant la suivante. Une option présélectionnée ou le temps écoulé ne constituent pas une réponse.

Examiner les règles existantes, les conséquences et le domaine concerné. Distinguer correction ponctuelle et convention à examiner globalement. Formuler la règle envisagée, son périmètre, ses critères de conformité et ses exceptions supposées sans les présenter comme approuvés.

Après avoir exploré ces sujets, restituer les décisions, exclusions, critères observables et points ouverts. Demander la confirmation explicite dans le chat, sans formulaire interactif, et attendre la réponse avant de documenter le cadrage. Une correction rouvre les questions concernées ; une décision nécessaire absente empêche de considérer le cadrage confirmé. Le silence ne vaut pas confirmation.

Après confirmation, appliquer le skill `ai-development-engineering-documenter-demande` pour rechercher ou créer le brouillon, avec le constat, les exemples disponibles et les questions pour l’analyse. Ne pas modifier le code, les conventions en vigueur ni leurs contrôles ; ne pas préparer de cartes ici : elles relèvent de l’étape 02 Analyse / découpage.

## Sortie et preuve

Proposition documentée, exemples du constat et critères de conformité à analyser ; aucune règle adoptée implicitement.

## Arrêt

Constat invérifiable ou intention ambiguë : préciser les informations manquantes sans inventer de règle.
