---
description: "Réunir les commits des cartes de consolidation validées sur une branche de demande depuis develop, avec traçabilité des SHA et contrôles."
---

# Consolidation · 05 Reconstitution

## Consignes impératives

Avant toute autre lecture liée à la mission, **lire impérativement les fichiers `AGENTS.md` applicables**, globaux et du projet, et respecter leurs consignes.

Consulter également la **documentation pertinente du dossier `docs/`** du projet concerné.

Prêter une attention particulière à la **qualité des réponses** et aux règles encadrant les **exécutions lourdes**, notamment les tests.

## Entrée

Demande de consolidation et toutes ses cartes commitées à l’étape 03 puis validées à l’étape 04, avec verdicts, SHA sources et ordre des dépendances.

## Procédure

Lire les instructions, les README, la demande et les cartes. Dans AIDE, appliquer la procédure commune `docs/architecture/03-developpement-loop/05-reconstitution.md`. La référence de consolidation est `docs/architecture/04-consolidation-loop/05-reconstitution.md`.

Rester concis et renvoyer aux décisions existantes sans les recopier.

Vérifier la disponibilité, la branche, l’index et tous les fichiers non suivis du dossier principal. Préserver les .env, données, fichiers locaux et worktrees. Ne pas déplacer une mission étrangère ni utiliser stash, reset destructif ou force-push.

L’invocation autorise la création de `demands/<identifiant>` depuis le develop local vérifié, dans le dossier principal libre et propre. Les couches conservent leurs branches.

Appliquer le skill `ai-development-engineering-appliquer-commits-valides` pour reprendre les seuls commits validés et leurs traces.

Lorsque la demande affecte `docs/`, appliquer après les cherry-picks le skill `ai-development-engineering-documenter-projet` pour intégrer les brouillons documentaires validés.

Après les cherry-picks, appliquer le skill `ai-development-engineering-materialiser-demande` pour créer ou reprendre le document définitif à partir du brouillon confirmé. Vérifier le diff, les liens et les contrôles.

Un conflit qui change le résultat validé demande une décision humaine ; ne pas valider une différence par déduction. Aucun nouveau développement, push, PR, fusion de livraison ou étape suivante automatique. Ne pas déléguer sans demande explicite.

## Sortie et preuve

**Résultat attendu :** Branche dédiée reconstituée, SHA sources et obtenus, contrôles et limites dans la trace de la demande, prête pour l’étape 06 Livraison.

## Arrêt

**Situation bloquante :** Carte non validée, commit manquant, dossier sale ou occupé, branche étrangère ou conflit hors du résultat validé : préserver le travail et exposer le blocage.

## Prochaine étape

Une fois la demande reconstituée et vérifiée, l’étape **06 Livraison** peut être engagée avec le prompt `ai-development-engineering-livrer-consolidation`, sur instruction explicite et sans enchaînement automatique.
