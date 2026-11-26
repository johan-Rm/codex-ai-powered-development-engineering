---
description: "Livrer une demande de développement avec contrôles CI/CD et fusion effectués par l’humain, puis suivi local par l’agent."
---

# Développement · 06 Livraison

## Consignes impératives

Avant toute autre lecture liée à la mission, **lire impérativement les fichiers `AGENTS.md` applicables**, globaux et du projet, et respecter leurs consignes.

Consulter également la **documentation pertinente du dossier `docs/`** du projet concerné.

Prêter une attention particulière à la **qualité des réponses** et aux règles encadrant les **exécutions lourdes**, notamment les tests.

## Entrée

Branche réunissant tous les commits de tâches validées et documentation à jour.

## Contexte et conventions du projet

Lire les instructions du projet, la demande ou carte fournie et les README applicables. Résoudre les chemins, couches, branches, commandes de tests et qualité depuis le projet ; annoncer les valeurs utilisées et les inconnues, sans imposer de valeurs personnelles.

Avant une écriture, confirmer le worktree absolu, la branche autorisée et la disponibilité de la couche. Préserver les modifications préexistantes et les `.env`. Ne pas utiliser stash, reset --hard, force-push ou suppression de worktree pour résoudre une situation.

Ne pas rebaser une branche occupée. L’invocation autorise les commits documentaires nécessaires, la vérification distante, le push sans forcer, l’ouverture de la PR vers `develop` et le suivi local après fusion.

Ne pas demander de confirmations intermédiaires pour les opérations autorisées par le projet. Dans AIDE, les nouvelles branches finales demands/* utilisent le dossier principal du dépôt ; les worktrees de couche restent sur layers/*.

Ne pas déplacer une demande ancienne déjà reconstituée dans une couche sans instruction explicite : reprendre son emplacement et sa branche de retour consignés. Aucune copie de réunion ni archivage à organiser. Préserver les worktrees, tmp/, .env, données et fichiers locaux.

Respecter une demande explicitement plus limitée, les protections distantes et les contrôles. Si le projet contredit ce périmètre, tenir compte des instructions explicites déjà accordées dans la session ; sinon signaler la contradiction sans contourner les règles.

L’alignement durable d’AGENTS.md et des guides reste à traiter lorsqu’une mise à jour provisoire des seuls skills a été demandée explicitement. **Ne pas déléguer sans autorisation.** **Ne pas enchaîner automatiquement une autre étape.**

## Procédure

Vérifier que l’étape 05 a réuni tous les commits validés sur une branche de demande. Ne pas refaire la reconstitution ni la remplacer par des merges de branches de couche. Contrôler la complétude, les verdicts, les SHA et le diff cumulé.

Inventorier avant livraison les worktrees, les missions, les modifications et les divergences locales. **Un arbre propre ne prouve pas la disponibilité** d’une couche.

Dans AIDE, lire les règles d’intégration et de suivi communes dans `docs/architecture/03-developpement-loop/06-livraison.md` et les autorisations `AGENTS.md`. Pour la consolidation, lire aussi sa page de livraison.

Ces références fixent les préconditions du réalignement après réécriture des SHA, sans les dupliquer. Respecter les limites explicites de l’utilisateur, notamment une demande limitée à la PR.

### Contrôles et PR

Pour les seules traces documentaires nécessaires et autorisées, appliquer le skill `ai-development-engineering-commit` avant les tests sur le HEAD final.

L’humain exécute les tests CI/CD préalables à l’ouverture de la PR sur le HEAD final à livrer. L’agent indique les commandes, le répertoire, les prérequis et les résultats attendus, puis vérifie les résultats transmis. Une preuve existante reste valable pour le même HEAD, les mêmes commandes et le même environnement.

Aucun contrôle inconnu ou échoué ne vaut réussite. Ne pas affaiblir une règle, un seuil ou une exception pour livrer ; une correction fonctionnelle retourne à la validation humaine.

Les nouveaux contrôles de consolidation disposent d’une commande stable et de cas conformes, écarts et exceptions testés.

Une fois les contrôles requis réussis sur le HEAD final, appliquer le skill `ai-development-engineering-creer-pr` pour préparer et ouvrir la PR autorisée.

### Intégration et suivi

L’humain vérifie les résultats des contrôles CI/CD de la PR et déclenche les éventuels contrôles manuels requis. Il effectue lui-même le **Rebase and merge** vers `develop` une fois les contrôles et protections satisfaits. L’agent transmet l’URL de la PR et attend la fusion humaine avant de reprendre le suivi. Une instruction limitée à la PR arrête la livraison à son ouverture.

Après intégration distante vérifiée, appliquer le skill `ai-development-engineering-suivre-integration` pour le suivi local autorisé et la traçabilité de la livraison. Ne pas annoncer la clôture si une couche reste non alignée.

## Sortie et preuve

**Résultat attendu :** Dossier de livraison contrôlé, URL réelle de PR, SHA de fusion et tableau des SHA de develop et de toutes les couches alignées après suivi ; en cas de blocage, stade atteint, éléments prêts et cause précise. Ne pas annoncer une opération non exécutée.

## Arrêt

**Situation bloquante :** Contrôle requis absent, inconnu ou échoué, arbre incomplet ou verdict manquant : exposer ce qui empêche la livraison.

## Fin de la boucle

La livraison termine la boucle lorsque ses conditions de clôture sont satisfaites. Une livraison limitée à la PR ou un suivi bloqué reste à poursuivre ; ne pas annoncer la boucle terminée prématurément.
