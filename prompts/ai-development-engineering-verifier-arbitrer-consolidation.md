---
description: "Vérifier avec l’humain une consolidation entièrement implémentée et commitée, puis tracer les verdicts sans recréer les commits de tâches."
---

# Consolidation · 04 Vérification / arbitrage

Avant toute autre lecture liée à la mission, lire le chapitre « Règles de rédaction des réponses et des documents » du `AGENTS.md` applicable.
Appliquer les règles de tests lourds du chapitre « Contrôles qualité et conditions de clôture du travail » d’AGENTS.md.

## Entrée

Demande entièrement implémentée, cartes et commits identifiés, tests, documentation
et preuves. L’humain peut explicitement limiter la vérification à certaines cartes.

## Conventions du projet

Lire les instructions du projet, la demande et ses cartes. Les instructions explicites
de l’utilisateur priment. Vérifier worktrees, branches, index et changements présents
avant toute écriture ; préserver travail étranger, `.env` et données.
Aucun stash, reset --hard, force-push ou rebase de branche occupée.
Ne pas déléguer ni enchaîner automatiquement une autre étape.

Les commits de tâches sont déjà créés à l’implémentation ; ils ne constituent pas un
verdict humain. L’invocation autorise les seules traces documentaires nécessaires
après verdict explicite. Aucun nouveau développement, push, PR ou merge ici.

## Procédure

Lire le brouillon de consolidation identifié dans le principal et les cartes de
`dev-book/tasks/` dans leurs couches. Ne pas créer la demande définitive ni demands/*.

Présenter la couverture de la demande complète, les comportements observables,
les critères, preuves, commandes et limites, associés aux SHA réellement implémentés.
Confronter les résultats aux arbitrages de l’étape 02 : occurrences couvertes, exceptions,
écarts détectés et cas conformes acceptés. Distinguer réussite du contrôle et adéquation
de la règle ; fournir les commandes reproductibles, préconditions et preuves positives
et négatives. Vérifier que le contenu présenté correspond toujours à ces commits et relever tout
diff supplémentaire. Ne pas réécrire l’historique pour imposer rétroactivement un format.

Attendre un verdict libre dans le chat, sans formulaire interactif : l’humain valide,
ajuste, diffère ou rejette. Une validation globale couvre seulement les cartes
présentées. Ne déduire aucun verdict du silence, des tests ou de l’invocation.

## Après le verdict

Associer fidèlement le verdict aux cartes et SHA examinés dans leurs traces et le
brouillon. Ne pas recréer les commits d’implémentation ni demander leur autorisation
à nouveau. Les seuls commits de cette étape sont les traces documentaires du verdict,
sur branches de mission et avec index limité aux fichiers concernés. Pour préparer et
créer ces commits autorisés, appliquer le skill `ai-development-engineering-commit`.

Une correction retourne à l’implémentation, puis à une nouvelle vérification ;
un changement de besoin retourne à l’analyse. Ne pas coder durant la vérification.
Conserver les commits existants ; aucun amend ni réécriture de branche partagée.

## Sortie et preuve

Verdict explicite de la demande, associé aux cartes et commits présentés ; couverture,
corrections et éventuels critères non vérifiés identifiés. Une demande acceptée reste
à reconstituer et à livrer selon les autorisations de ces étapes.

## Arrêt

Preuve manquante, verdict absent, contenu différent des commits présentés ou périmètre
ambigu : préserver le travail et signaler les points à résoudre sans inventer de validation.
