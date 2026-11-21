---
description: "Clarifier une demande de développement avec l’humain et documenter le besoin avant son découpage."
---

# Développement · 01 Interview

Avant toute autre lecture liée à la mission, lire le chapitre « Règles de rédaction des réponses et des documents » du `AGENTS.md` applicable.
Appliquer les règles de tests lourds du chapitre « Contrôles qualité et conditions de clôture du travail » d’AGENTS.md.

## Entrée

Demande humaine, contexte et documentation produit disponibles.

## Conventions du projet

Lire les instructions du projet, la demande ou carte fournie et les README applicables.
Les instructions explicites de l’utilisateur priment sur les règles locales.
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

Examiner le problème et sa motivation, les utilisateurs et usages, le périmètre et les exclusions,
le comportement attendu, les contraintes, les cas limites, les critères d’acceptation,
les preuves et tests attendus ainsi que la documentation concernée. Poser toutes les questions
utiles au résultat, même pour une demande présentée comme simple ; éviter les questions artificielles
ou sans incidence. Pour chaque dimension, s’appuyer sur une réponse humaine, une décision existante
ou une justification de son absence de pertinence. Garder visibles les questions non résolues.

Après avoir exploré ces sujets, restituer les décisions, exclusions, critères observables et points ouverts. Demander la confirmation explicite dans le chat, sans formulaire interactif, et attendre la réponse avant de documenter le cadrage. Une correction rouvre les questions concernées ; une décision nécessaire absente empêche de considérer le cadrage confirmé. Le silence ne vaut pas confirmation.

### Documentation du cadrage

Après confirmation, appliquer le skill `ai-development-engineering-documenter-demande` pour rechercher ou créer le brouillon.

Le fichier fait référence pour le besoin, le contexte, les utilisateurs concernés, les critères
observables, les contraintes, les exclusions, les questions ouvertes et les décisions humaines.
Conserver l’identifiant, le titre, la date, l’état du cadrage et sa confirmation humaine.
Le chat sert à construire et préciser la demande. Son lien est facultatif et distinct de l’identifiant de session obligatoire.
Une carte externe de suivi est facultative. Conserver son lien ne nécessite aucune connexion ;
la créer ou la modifier requiert une instruction explicite. L’absence de lien vers le chat
ou de carte externe n’empêche pas le cadrage ; l’identifiant de session reste obligatoire. Prévoir une rubrique pour les tâches issues du découpage ; cette étape
ajoutera les liens vers les cartes et chaque carte référencera la demande d’origine.
Ne créer ni cartes ni branches et ne pas lancer le découpage.
Une décision de besoin ne vaut pas validation d’un résultat implémenté.

## Sortie et preuve

Demande cadrée et référencée, décisions humaines et critères observables. Preuve : restitution confirmée et chemin du document.

## Arrêt

Besoin contradictoire ou décision nécessaire absente : garder les questions ouvertes et ne pas présenter la demande comme prête.
