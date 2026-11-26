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

Pour une nouvelle reconstitution, reprendre le nom fixé au découpage au format `demands/<identifiant>-<sujet>`, par exemple `demands/DEM-022-validation-manuelle-des-tests`. Si le découpage ne précise aucun sujet, le dériver du titre confirmé de la demande. Utiliser un sujet court composé de lettres ASCII minuscules, de chiffres et de tirets. Si la demande est déjà reconstituée, vérifier et réutiliser sa branche existante, y compris si elle porte l’ancien nom.

L’invocation autorise la création de `demands/<identifiant>-<sujet>` depuis le develop local vérifié, dans le dossier principal libre et propre. Les couches conservent leurs branches.

Appliquer le skill `ai-development-engineering-appliquer-commits-valides` pour reprendre les seuls commits validés et leurs traces.

Lorsque la demande affecte `docs/`, appliquer après les cherry-picks le skill `ai-development-engineering-documenter-projet` pour intégrer les brouillons documentaires validés.

Après les cherry-picks, appliquer le skill `ai-development-engineering-materialiser-demande` pour créer ou reprendre le document définitif à partir du brouillon confirmé. Vérifier le diff, les liens et les contrôles.

Un conflit qui change le résultat validé demande une décision humaine ; ne pas valider une différence par déduction. Aucun nouveau développement, push, PR, fusion de livraison ou étape suivante automatique. Ne pas déléguer sans demande explicite.

Une fois la reconstitution terminée, lire le fichier `TEST.md` du dossier principal. Demander à l’humain d’y lancer manuellement la suite complète sur la branche reconstituée. Indiquer le chemin absolu du dossier principal, le SHA à tester, les commandes de `TEST.md`, leurs prérequis et les résultats attendus. Attendre le retour de l’humain et consigner le résultat communiqué et le SHA correspondant dans la trace de la demande. Si `TEST.md` est introuvable, signaler le blocage.

## Sortie et preuve

**Résultat attendu :** Branche dédiée reconstituée, SHA sources et obtenus, contrôles et limites dans la trace de la demande.

## Arrêt

**Situation bloquante :** Carte non validée, commit manquant, dossier sale ou occupé, branche étrangère ou conflit hors du résultat validé : préserver le travail et exposer le blocage.

Préparer le titre et le corps du commit unique attendu dans `develop` selon la [référence Git AIDE](../skills/references/git-workflow.md#intégration-et-suivi). Conserver les commits de cartes sur la branche reconstituée pour les contrôles et la traçabilité.

## Prochaine étape

Après confirmation humaine de la réussite de la suite complète sur le SHA final reconstitué, l’étape **06 Livraison** peut être engagée avec le prompt `ai-development-engineering-livrer-consolidation`, sur instruction explicite et sans enchaînement automatique.
