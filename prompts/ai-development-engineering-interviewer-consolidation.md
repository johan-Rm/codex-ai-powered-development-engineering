---
description: "Clarifier un constat de consolidation et documenter une proposition de convention technique à examiner."
---

# Consolidation · 01 Interview

## Consignes impératives

Avant toute autre lecture liée à la mission, **lire impérativement les fichiers `AGENTS.md` applicables**, globaux et du projet, et respecter leurs consignes.

Consulter également la **documentation pertinente du dossier `docs/`** du projet concerné.

Prêter une attention particulière à la **qualité des réponses** et aux règles encadrant les **exécutions lourdes**, notamment les tests.

## Entrée

Le constat de consolidation peut être **formulé directement par l’humain dans la session** ou **provenir d’un outil tiers de gestion de projet**, par exemple sous la forme d’une carte ou d’un ticket. Il peut également résulter d’une revue ou d’une observation ; aucune demande de développement préalable n’est nécessaire.

S’appuyer sur le constat et sur les éléments de contexte et de documentation disponibles pour préparer l’échange. Si le constat provient d’un outil tiers, conserver sa référence afin de pouvoir retrouver la source.

## Contexte de la demande

Identifier le **projet concerné** et prendre connaissance des instructions applicables et des documents liés à la demande.

S’appuyer sur les informations disponibles pour préparer l’interview. Signaler les **éléments manquants ou incertains** et les clarifier avec l’humain lorsqu’ils sont nécessaires.

Respecter le périmètre demandé et préserver les éléments existants. **Ne pas déléguer ni passer à une autre étape** sans instruction explicite.

## Procédure

Rechercher une demande ou un brouillon existant et lire les décisions déjà prises. Distinguer **faits, hypothèses, propositions et questions ouvertes**. Ne pas redemander une décision déjà prise ni présenter une proposition comme approuvée.

Conduire l’échange avec `request_user_input_async`, ou `request_user_input` si le mode actif l’autorise. Sans outil interactif disponible, poursuivre directement dans le chat.

Poser **une question à la fois**, avec des choix concrets et une réponse libre lorsque cela aide ; attendre la réponse avant la suivante. Une option présélectionnée ou le temps écoulé ne constituent pas une réponse.

Examiner :

- les **règles existantes**, leurs conséquences et le domaine concerné ;
- la distinction entre **correction ponctuelle et convention** à examiner globalement ;
- la **règle envisagée**, son périmètre, ses critères de conformité et ses exceptions supposées, sans les présenter comme approuvés.

Après avoir exploré ces sujets, restituer les **décisions, exclusions, critères observables et points ouverts**. Demander la **confirmation explicite dans le chat**, sans formulaire interactif, et attendre la réponse avant de documenter le cadrage.

Une correction rouvre les questions concernées ; une décision nécessaire absente empêche de considérer le cadrage confirmé. Le silence ne vaut pas confirmation.

### Documentation du cadrage

Après confirmation, appliquer le skill `ai-development-engineering-documenter-demande` pour documenter le brouillon, avec le constat, les exemples disponibles et les questions pour l’analyse.

**Ne pas modifier le code, les conventions en vigueur ni leurs contrôles.** Ne pas lancer le découpage : il relève de l’étape 02 Analyse / découpage.

## Sortie et preuve

**Sortie :** proposition documentée, exemples du constat et critères de conformité à analyser ; aucune règle adoptée implicitement.

**Preuve :** restitution confirmée et chemin du document.

## Arrêt

En cas de **constat invérifiable** ou d’**intention ambiguë**, préciser les informations manquantes sans inventer de règle.

## Prochaine étape

Une fois le cadrage confirmé et documenté, l’étape **02 Analyse / découpage** peut être engagée avec le prompt `ai-development-engineering-analyser-decouper-consolidation`, sur instruction explicite et sans enchaînement automatique.
