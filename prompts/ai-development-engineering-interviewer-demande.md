---
description: "Clarifier une demande de développement avec l’humain et documenter le besoin avant son découpage."
---

# Développement · 01 Interview

## Consignes impératives

Avant toute autre lecture liée à la mission, **lire impérativement les fichiers `AGENTS.md` applicables**, globaux et du projet, et respecter leurs consignes.

Consulter également la **documentation pertinente du dossier `docs/`** du projet concerné.

Prêter une attention particulière à la **qualité des réponses** et aux règles encadrant les **exécutions lourdes**, notamment les tests.

## Entrée

La demande de développement peut être **formulée directement par l’humain dans la session** ou **provenir d’un outil tiers de gestion de projet**, par exemple sous la forme d’une carte ou d’un ticket.

S’appuyer sur la demande et sur les éléments de contexte et de documentation produit disponibles pour préparer l’échange. Si la demande provient d’un outil tiers, conserver sa référence afin de pouvoir retrouver la source.

## Contexte de la demande

Identifier le **projet concerné** et prendre connaissance des instructions applicables et des documents liés à la demande.

S’appuyer sur les informations disponibles pour préparer l’interview. Signaler les **éléments manquants ou incertains** et les clarifier avec l’humain lorsqu’ils sont nécessaires.

Respecter le périmètre demandé et préserver les éléments existants. **Ne pas déléguer ni passer à une autre étape** sans instruction explicite.

## Procédure

Rechercher une demande ou un brouillon existant et lire les décisions déjà prises. Distinguer **faits, hypothèses, propositions et questions ouvertes**. Ne pas redemander une décision déjà prise ni présenter une proposition comme approuvée.

Conduire l’échange avec `request_user_input_async`, ou `request_user_input` si le mode actif l’autorise. Sans outil interactif disponible, poursuivre directement dans le chat.

Poser **une question à la fois**, avec des choix concrets et une réponse libre lorsque cela aide ; attendre la réponse avant la suivante. Une option présélectionnée ou le temps écoulé ne constituent pas une réponse.

Examiner :

- le **problème et sa motivation**, les utilisateurs et leurs usages ;
- le **périmètre et les exclusions**, le comportement attendu et les contraintes ;
- les **cas limites et critères d’acceptation**, les preuves et tests attendus ;
- la **documentation concernée**.

Poser toutes les questions utiles au résultat, même pour une demande présentée comme simple ; éviter les questions artificielles ou sans incidence. Pour chaque dimension, s’appuyer sur une réponse humaine, une décision existante ou une justification de son absence de pertinence. Garder visibles les questions non résolues.

Après avoir exploré ces sujets, restituer les **décisions, exclusions, critères observables et points ouverts**. Demander la **confirmation explicite dans le chat**, sans formulaire interactif, et attendre la réponse avant de documenter le cadrage.

Une correction rouvre les questions concernées ; une décision nécessaire absente empêche de considérer le cadrage confirmé. Le silence ne vaut pas confirmation.

### Documentation du cadrage

Après confirmation, appliquer le skill `ai-development-engineering-documenter-demande` pour documenter le brouillon.

Le fichier fait référence pour le besoin, le contexte, les utilisateurs concernés, les critères observables, les contraintes, les exclusions, les questions ouvertes et les décisions humaines. Conserver **l’identifiant, le titre, la date, l’état du cadrage et sa confirmation humaine**.

Le chat sert à construire et préciser la demande ; son lien est facultatif.

Une carte externe de suivi est facultative. Conserver son lien ne nécessite aucune connexion ; la créer ou la modifier requiert une instruction explicite. L’absence de lien vers le chat ou de carte externe n’empêche pas le cadrage.

Prévoir une rubrique pour les tâches issues du découpage ; cette étape ajoutera les liens vers les cartes et chaque carte référencera la demande d’origine.

**Ne pas lancer le découpage.** Une décision de besoin ne vaut pas validation d’un résultat implémenté.

## Sortie et preuve

**Sortie :** demande cadrée et référencée, décisions humaines et critères observables.

**Preuve :** restitution confirmée et chemin du document.

## Arrêt

En cas de **besoin contradictoire** ou de **décision nécessaire absente**, garder les questions ouvertes et ne pas présenter la demande comme prête.

## Prochaine étape

Une fois le cadrage confirmé et documenté, l’étape **02 Analyse / découpage** peut être engagée avec le prompt `ai-development-engineering-analyser-decouper-demande`, sur instruction explicite et sans enchaînement automatique.
