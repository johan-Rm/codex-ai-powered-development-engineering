---
description: "Créer la branche d’une demande depuis develop et y cherry-pick les commits validés."
---

# Développement · 05 Reconstitution

## Consignes impératives

Avant toute autre lecture liée à la mission, **lire impérativement les fichiers `AGENTS.md` applicables**, globaux et du projet, et respecter leurs consignes.

Consulter également la **documentation pertinente du dossier `docs/`** du projet concerné.

Prêter une attention particulière à la **qualité des réponses** et aux règles encadrant les **exécutions lourdes**, notamment les tests.

## Entrée

Demande, cartes validées, SHA de leurs commits et branche dédiée prévue au découpage.

## Procédure

Lire les consignes du projet, la demande, les cartes et les README applicables. Les instructions explicites de l’utilisateur priment sur les règles locales. Vérifier que toutes les cartes attendues sont validées et commitées.

Inclure les commits de verdict nécessaires et respecter l’ordre des dépendances.

Dans AIDE, utiliser le dossier principal du dépôt, pas un worktree de couche. Résoudre son chemin absolu depuis git worktree list, sans confondre cette racine avec git rev-parse --show-toplevel exécuté dans un worktree lié.

Vérifier sa branche, son index, les fichiers non suivis et les missions actives. Pour une nouvelle reconstitution, le principal doit être libre et propre, sur develop.

S’il porte une autre demande ou des changements étrangers, signaler le blocage sans déplacement, stash ou nettoyage.

Une reprise de la même demande conserve ses changements identifiés après vérification ; ne pas déplacer une demande ancienne déjà reconstituée dans une couche sans instruction explicite. Préserver tmp/, les .env, données et fichiers locaux.

Ne créer ni nouveau worktree, copie ou dossier de réunion. Les worktrees de couche restent sur layers/*.

Dans le principal, créer `demands/<identifiant>` depuis le develop local explicitement vérifié : `git switch -c demands/<identifiant> develop`. Ne pas modifier directement develop ou production.

Une branche existante n’est pas déplacée : vérifier sa provenance et reprendre seulement la même demande. Noter develop comme branche à retrouver dans le principal après fusion distante.

Appliquer le skill `ai-development-engineering-appliquer-commits-valides` pour reprendre les seuls commits validés et leurs traces sur la branche de demande.

Lorsque la demande affecte `docs/`, appliquer après les cherry-picks le skill `ai-development-engineering-documenter-projet` pour intégrer les brouillons documentaires validés.

Après les cherry-picks, appliquer le skill `ai-development-engineering-materialiser-demande` pour créer ou reprendre le document définitif à partir du brouillon confirmé.

Vérifier le diff final, les liens et les contrôles pertinents. Un conflit se résout uniquement dans le périmètre validé ; si sa résolution change le comportement, attendre une décision humaine. Ne pas revalider un résultat différent par déduction.

L’invocation autorise la création de branche et les cherry-picks du périmètre prévu ; respecter les restrictions explicites du projet et de l’utilisateur. Ne pas stasher, reset destructivement, forcer une référence ou rebaser une branche occupée.

Aucune délégation, push, PR, fusion de livraison ou étape suivante automatique.

## Sortie et preuve

**Résultat attendu :** Branche dédiée reconstituée, correspondance des SHA sources et obtenus, diff et contrôles, limites éventuelles consignés dans la demande ou les cartes.

## Arrêt

**Situation bloquante :** Carte non validée, commit absent, worktree sale ou occupé, branche étrangère ou conflit hors du résultat validé : préserver le travail et signaler le blocage.