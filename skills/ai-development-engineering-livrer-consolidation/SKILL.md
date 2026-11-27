---
name: ai-development-engineering-livrer-consolidation
description: "Livrer une consolidation validée avec contrôles CI/CD et fusion effectués par l’humain, puis suivi local par l’agent."
---

# Consolidation · 05 Livraison

## Consignes impératives

Avant toute autre lecture liée à la mission, **lire impérativement les fichiers `AGENTS.md` applicables**, globaux et du projet, et respecter leurs consignes.

Consulter également la **documentation pertinente du dossier `docs/`** du projet concerné.

Prêter une attention particulière à la **qualité des réponses** et aux règles encadrant les **exécutions lourdes**, notamment les tests.

## Entrée

Branche de consolidation validée à l’étape 05, cartes validées et commitées, SHA et destinations autorisées.

## Contexte et conventions du projet

Lire les instructions du projet, la demande ou carte fournie et les README applicables. Résoudre les chemins, couches, branches, commandes de tests et qualité depuis le projet ; annoncer les valeurs utilisées et les inconnues, sans imposer de valeurs personnelles.

Avant une écriture, confirmer le worktree absolu, la branche autorisée et la disponibilité du worktree de la demande. Préserver les modifications préexistantes et les `.env`. Ne pas utiliser stash, reset --hard, force-push ou suppression de worktree pour résoudre une situation.

Ne pas rebaser une branche occupée.

L’invocation autorise les commits documentaires nécessaires, la vérification distante et le fetch, le push sans forcer, l’ouverture de la PR vers `develop` et le suivi local après fusion.

Ne pas redemander confirmation. Une instruction limitée à la PR ou une restriction explicite du projet ou de l’utilisateur conserve sa limite. **Ne pas déléguer sans autorisation.** **Ne pas enchaîner automatiquement une autre étape.**

## Procédure

Vérifier que tous les commits et verdicts attendus sont présents sur la branche unique de la demande ; contrôler la complétude, les SHA et le diff cumulé.

Inventorier avant livraison les worktrees, les missions, les modifications et les divergences locales. **Un arbre propre ne prouve pas la disponibilité** du worktree.

Lire les règles d’intégration et de suivi du projet et les autorisations `AGENTS.md`. Si elles imposent encore la reconstitution ou les couches permanentes, signaler leur divergence et respecter les instructions explicites de l’utilisateur.

Respecter les préconditions de suivi applicables après intégration du commit unique. Respecter les limites explicites de l’utilisateur, notamment une demande limitée à la PR.

### Contrôles et PR

Pour les seules traces documentaires nécessaires et autorisées, appliquer le skill `ai-development-engineering-commit` avant les tests sur le HEAD final.

Lire `TEST.md` à la racine du worktree de la demande. Indiquer à l’humain le chemin absolu, le SHA final, les commandes, prérequis et résultats attendus ; lui demander d’exécuter la suite complète et consigner son résultat et ce SHA dans une preuve locale hors HEAD testé ou dans la PR. Si `TEST.md` manque ou le résultat est absent ou échoué, bloquer la livraison. Si un nouveau commit est nécessaire après les tests, refaire les contrôles requis sur le nouveau HEAD ; ne pas modifier le HEAD testé pour consigner leur résultat.

L’humain exécute les tests CI/CD préalables à l’ouverture de la PR sur le HEAD final à livrer. L’agent indique les commandes, le répertoire, les prérequis et les résultats attendus, puis vérifie les résultats transmis. Une preuve existante reste valable pour le même HEAD, les mêmes commandes et le même environnement.

Aucun contrôle inconnu ou échoué ne vaut réussite. Ne pas affaiblir une règle, un seuil ou une exception pour livrer ; une correction fonctionnelle retourne à la validation humaine.

Les nouveaux contrôles de consolidation disposent d’une commande stable et de cas conformes, écarts et exceptions testés.

Une fois les contrôles requis réussis sur le HEAD final, appliquer le skill `ai-development-engineering-creer-pr` pour préparer et ouvrir la PR autorisée.

### Intégration et suivi

L’humain vérifie les résultats des contrôles CI/CD de la PR et déclenche les éventuels contrôles manuels requis. Une fois les contrôles et protections satisfaits, il effectue lui-même le **Squash and merge** vers `develop` avec le message de commit préparé pour la livraison. L’agent vérifie que la PR couvre une seule demande et transmet le message final avec le lien de la PR. L’agent attend la fusion humaine avant de reprendre le suivi. Une instruction limitée à la PR arrête la livraison à son ouverture.

Après intégration distante vérifiée, appliquer le skill `ai-development-engineering-suivre-integration` pour le suivi local autorisé et la traçabilité de la livraison.

## Sortie et preuve

**Résultat attendu :** Contributions contrôlées, commandes durables et dossiers de PR ; URLs seulement pour les PRs autorisées et réellement ouvertes ; SHA de fusion et suivi local lorsque demandés.

## Arrêt

**Situation bloquante :** Carte non validée, occurrence oubliée, contrôle requis inconnu ou échoué : ne pas ouvrir de PR et exposer le travail restant.

## Fin de la boucle

La livraison termine la boucle lorsque ses conditions de clôture sont satisfaites. Une livraison limitée à la PR ou un suivi bloqué reste à poursuivre ; ne pas annoncer la boucle terminée prématurément.
