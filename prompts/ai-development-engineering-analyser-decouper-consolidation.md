---
description: "Analyser une convention dans toute la base, confirmer les décisions nécessaires et préparer toutes les cartes de consolidation."
---

# Consolidation · 02 Analyse / découpage

## Consignes impératives

Avant toute autre lecture liée à la mission, **lire impérativement les fichiers `AGENTS.md` applicables**, globaux et du projet, et respecter leurs consignes.

Consulter également la **documentation pertinente du dossier `docs/`** du projet concerné.

Prêter une attention particulière à la **qualité des réponses** et aux règles encadrant les **exécutions lourdes**, notamment les tests.

## Entrée

Proposition de convention et périmètre à analyser ; aucun livrable de développement requis.

## Contexte et conventions du projet

Lire les instructions du projet, la demande ou carte fournie et les README applicables. Résoudre les chemins, couches, branches, commandes de tests et qualité depuis le projet ; annoncer les valeurs utilisées et les inconnues, sans imposer de valeurs personnelles.

Avant une écriture, confirmer le worktree absolu, la branche autorisée et la disponibilité de la couche. Préserver les modifications préexistantes et les `.env`. Ne pas utiliser stash, reset --hard, force-push ou suppression de worktree pour résoudre une situation.

Ne pas rebaser une branche occupée. Commit, push, PR et merge nécessitent l’autorisation prévue par le projet ; une invocation d’étape ne les autorise pas implicitement. Les autorisations explicites déjà données restent valables.

**Ne pas déléguer sans autorisation.** **Ne pas enchaîner automatiquement une autre étape.**

## Procédure

Examiner toutes les zones concernées par la règle, en respectant les exclusions du projet et sans parcourir les copies de worktrees comme des occurrences supplémentaires. Relever fichiers, occurrences conformes, écarts, exceptions et limites.

Distinguer ce qui a été lu de ce qui reste non vérifié. Rechercher les contrôles existants, leur portée et leurs angles morts.

Proposer les corrections et un contrôle déterministe avec cas conformes, écarts détectables et exceptions ; distinguer règle documentée et règle déjà contrôlée. Comparer les options et leurs coûts, niveaux bloquants et impacts par couche.

Documenter l’analyse dans le brouillon `tmp/demande-<sujet>.md` du dépôt principal, sans modifier code, contrôles ou conventions. Un état Git ou un échantillon ne prouve pas une analyse globale ; expliciter toute zone inaccessible.

### Confirmer puis découper

Présenter les options, leurs coûts, corrections, exceptions et contrôles proposés (bloquants ou informatifs). Faire confirmer explicitement la règle, sa portée, les exceptions et contrôles nécessaires à l’implémentation ; consigner exactement la décision.

Une décision déjà explicite reste acquise. **Le silence ne vaut pas accord.** Sans décision suffisante, conserver la proposition en attente, sans code ni contrôle modifié.

Appliquer le skill `ai-development-engineering-preparer-cartes` pour préparer toutes les cartes, leur matrice, les dépendances et les branches des couches affectées selon les autorisations du projet. Ne pas implémenter, committer, pousser ni appeler l’étape suivante.

## Sortie et preuve

**Résultat attendu :** Analyse référencée et couverture explicite, décisions initiales confirmées, toutes les cartes prêtes avec leurs critères et preuves. La vérification / arbitrage du résultat intervient à l’étape 04.

## Arrêt

**Situation bloquante :** Zone essentielle inaccessible ou périmètre inconnu : signaler la couverture incomplète avant arbitrage.
