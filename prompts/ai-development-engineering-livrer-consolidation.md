---
description: "Livrer une consolidation déjà reconstituée : contrôles, PR, Rebase and merge et suivi autorisé, sans refaire l’étape 05."
---

# Consolidation · 06 Livraison

## Consignes impératives

Avant toute autre lecture liée à la mission, **lire impérativement les fichiers `AGENTS.md` applicables**, globaux et du projet, et respecter leurs consignes.

Consulter également la **documentation pertinente du dossier `docs/`** du projet concerné.

Prêter une attention particulière à la **qualité des réponses** et aux règles encadrant les **exécutions lourdes**, notamment les tests.

## Entrée

Branche de consolidation reconstituée à l’étape 05, cartes validées et commitées, SHA et destinations autorisées.

## Contexte et conventions du projet

Lire les instructions du projet, la demande ou carte fournie et les README applicables. Résoudre les chemins, couches, branches, commandes de tests et qualité depuis le projet ; annoncer les valeurs utilisées et les inconnues, sans imposer de valeurs personnelles.

Avant une écriture, confirmer le worktree absolu, la branche autorisée et la disponibilité de la couche. Préserver les modifications préexistantes et les `.env`. Ne pas utiliser stash, reset --hard, force-push ou suppression de worktree pour résoudre une situation.

Ne pas rebaser une branche occupée.

L’invocation autorise la livraison complète depuis la branche reconstituée : commits documentaires nécessaires, vérification distante et fetch, push sans forcer, PR vers l’intégration, fusion après contrôles et protections satisfaits, suivi local et suppression des branches temporaires livrées.

Ne pas redemander confirmation. Une instruction limitée à la PR ou une restriction explicite du projet ou de l’utilisateur conserve sa limite. **Ne pas déléguer sans autorisation.** **Ne pas enchaîner automatiquement une autre étape.**

## Procédure

Vérifier que l’étape 05 a réuni tous les commits validés sur une branche de demande. Ne pas refaire la reconstitution ni la remplacer par des merges de branches de couche. Contrôler la complétude, les verdicts, les SHA et le diff cumulé.

Inventorier avant livraison les worktrees, les missions, les modifications et les divergences locales. **Un arbre propre ne prouve pas la disponibilité** d’une couche.

Dans AIDE, lire les règles d’intégration et de suivi communes dans `docs/architecture/03-developpement-loop/06-livraison.md` et les autorisations `AGENTS.md`. Pour la consolidation, lire aussi sa page de livraison.

Ces références fixent les préconditions du réalignement après réécriture des SHA, sans les dupliquer. Respecter les limites explicites de l’utilisateur, notamment une demande limitée à la PR.

### Contrôles et PR

Faire réaliser les contrôles requis sur la branche reconstituée selon la règle commune et attendre leurs résultats. Une preuve déjà lue portant sur le même HEAD, les mêmes commandes et le même environnement peut éviter une répétition identique.

Aucun contrôle inconnu ou échoué ne vaut réussite. Ne pas affaiblir une règle, un seuil ou une exception pour livrer ; une correction fonctionnelle retourne à la validation humaine.

Les nouveaux contrôles de consolidation disposent d’une commande stable et de cas conformes, écarts et exceptions testés.

Pour les seules traces documentaires nécessaires et autorisées, appliquer le skill `ai-development-engineering-commit`. Appliquer ensuite le skill `ai-development-engineering-creer-pr` pour préparer et ouvrir la PR autorisée, après réussite des contrôles requis.

### Intégration et suivi

Si la fusion est autorisée et que les contrôles et protections sont satisfaits, appliquer le skill `ai-development-engineering-fusionner-pr`. Une instruction limitée à la PR arrête la livraison à cette étape.

Après intégration distante vérifiée, appliquer le skill `ai-development-engineering-suivre-integration` pour le suivi local autorisé et la traçabilité de la livraison. Ne pas annoncer la clôture si une couche reste non alignée.

## Sortie et preuve

**Résultat attendu :** Contributions contrôlées, commandes durables et dossiers de PR ; URLs seulement pour les PRs autorisées et réellement ouvertes ; SHA de fusion et suivi local lorsque demandés.

## Arrêt

**Situation bloquante :** Carte non validée, occurrence oubliée, contrôle requis inconnu ou échoué : ne pas ouvrir de PR et exposer le travail restant.
