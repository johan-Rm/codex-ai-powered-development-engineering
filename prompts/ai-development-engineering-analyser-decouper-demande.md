---
description: "Analyser une demande de développement, ses impacts et dépendances, puis préparer toutes ses cartes et missions."
---

# Développement · 02 Analyse / découpage

## Consignes impératives

Avant toute autre lecture liée à la mission, **lire impérativement les fichiers `AGENTS.md` applicables**, globaux et du projet, et respecter leurs consignes.

Consulter également la **documentation pertinente du dossier `docs/`** du projet concerné.

Prêter une attention particulière à la **qualité des réponses** et aux règles encadrant les **exécutions lourdes**, notamment les tests.

## Entrée

Demande cadrée et décisions humaines identifiées.

## Contexte et conventions du projet

Lire les instructions du projet, la demande ou carte fournie et les README applicables. Les instructions explicites de l’utilisateur priment sur les règles locales.

Résoudre les chemins, couches, branches, commandes de tests et qualité depuis le projet ; annoncer les valeurs utilisées et les inconnues, sans imposer de valeurs personnelles. Avant une écriture, confirmer le worktree absolu, la branche autorisée et la disponibilité de la couche.

Préserver les modifications préexistantes et les `.env`. Ne pas utiliser stash, reset --hard, force-push ou suppression de worktree pour résoudre une situation. Ne pas rebaser une branche occupée.

Respecter les autorisations Git du projet : une invocation peut autoriser les commits locaux prévus par cette étape si le projet le définit explicitement. Push, PR et merge restent soumis à leurs autorisations propres. Conserver les autorisations explicites déjà données.

**Ne pas déléguer sans autorisation.** **Ne pas enchaîner automatiquement une autre étape.**

## Procédure

Analyser le besoin, les impacts et les conventions applicables avant de découper. Comparer les options utiles et faire confirmer les décisions de besoin encore ouvertes, sans redemander celles déjà explicites. La sortie couvre toutes les cartes de la demande.

Appliquer le skill `ai-development-engineering-preparer-cartes` pour préparer toutes les cartes, leur matrice, les dépendances et les branches des couches affectées selon les autorisations du projet.

Réaliser le découpage en autonomie ; questionner seulement une décision de besoin manquante. Ne pas implémenter les cartes.

## Sortie et preuve

**Résultat attendu :** Cartes et matrice demande/tâches, ordre et dépendances, état réel des branches préparées. Preuve : chemins des cartes et états Git observés.

## Arrêt

**Situation bloquante :** Couche occupée, identifiant ambigu ou dépendance de réalisation sans commit : signaler les missions non prêtes sans copier le travail non commité.

## Prochaine étape

Une fois l’analyse et les cartes prêtes, l’étape **03 Implémentation** peut être engagée avec le prompt `ai-development-engineering-implementer-demande`, sur instruction explicite et sans enchaînement automatique.
