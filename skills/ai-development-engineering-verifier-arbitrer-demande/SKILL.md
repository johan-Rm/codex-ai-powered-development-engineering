---
name: ai-development-engineering-verifier-arbitrer-demande
description: "Accompagner la vérification humaine d’une demande entièrement implémentée et commitée, puis tracer les verdicts sans recréer les commits de tâches."
---

# Développement · 04 Vérification / arbitrage

## Consignes impératives

Avant toute autre lecture liée à la mission, **lire impérativement les fichiers `AGENTS.md` applicables**, globaux et du projet, et respecter leurs consignes.

Consulter également la **documentation pertinente du dossier `docs/`** du projet concerné.

Prêter une attention particulière à la **qualité des réponses** et aux règles encadrant les **exécutions lourdes**, notamment les tests.

## Entrée

Demande entièrement implémentée, cartes et commits identifiés, tests, documentation et preuves. L’humain peut explicitement limiter la vérification à certaines cartes.

## Contexte et conventions du projet

Lire les instructions du projet, la demande et ses cartes. Les instructions explicites de l’utilisateur priment. Vérifier worktrees, branches, index et changements présents avant toute écriture ; préserver travail étranger, `.env` et données.

Aucun stash, reset --hard, force-push ou rebase de branche occupée. Ne pas déléguer ni enchaîner automatiquement une autre étape.

Les commits de tâches sont déjà créés à l’implémentation ; ils ne constituent pas un verdict humain. L’invocation autorise les seules traces documentaires nécessaires après verdict explicite. Aucun nouveau développement, push, PR ou merge ici.

## Procédure

Lire la demande, les cartes et les commits dans le worktree unique. Examiner pour chaque tâche son objectif, le résultat obtenu et les éventuelles dérives du code ou du périmètre. La validation humaine intervient après l’ensemble des commits présentés.

Présenter la couverture de la demande complète, les comportements observables, les critères, preuves, commandes et limites, associés aux SHA réellement implémentés. Vérifier que le contenu présenté correspond toujours à ces commits et relever tout diff supplémentaire.

Ne pas réécrire l’historique pour imposer rétroactivement un format.

Attendre un verdict libre dans le chat, sans formulaire interactif : l’humain valide, ajuste, diffère ou rejette. Une validation globale couvre seulement les cartes présentées. **Ne déduire aucun verdict du silence, des tests ou de l’invocation.**

## Après le verdict

Après verdict explicite, appliquer le skill `ai-development-engineering-tracer-verdict` pour le rattacher aux cartes et commits examinés et créer les seules traces documentaires autorisées.

Une correction retourne à l’implémentation, puis à une nouvelle vérification ; un changement de besoin retourne à l’analyse. Ne pas coder durant la vérification. Conserver les commits existants ; aucun amend ni réécriture de branche partagée.

## Sortie et preuve

**Résultat attendu :** Verdict explicite de la demande, associé aux cartes et commits présentés ; couverture, corrections et éventuels critères non vérifiés identifiés. Une demande acceptée reste à préparer pour livraison.

## Arrêt

**Situation bloquante :** Preuve manquante, verdict absent, contenu différent des commits présentés ou périmètre ambigu : préserver le travail et signaler les points à résoudre sans inventer de validation.

## Prochaine étape

Une fois les cartes nécessaires validées, l’étape **05 Livraison** peut être engagée avec le skill `ai-development-engineering-livrer-demande`, sur instruction explicite et sans enchaînement automatique.
