---
description: "Livrer une consolidation déjà reconstituée : contrôles, PR, Rebase and merge et suivi autorisé, sans refaire l’étape 05."
---

# Consolidation · 06 Livraison

Avant toute autre lecture liée à la mission, lire le chapitre « Règles de rédaction des réponses et des documents » du `AGENTS.md` applicable.
Appliquer les règles de tests lourds du chapitre « Contrôles qualité et conditions de clôture du travail » d’AGENTS.md.

## Entrée

Branche de consolidation reconstituée à l’étape 05, cartes validées et commitées, SHA et destinations autorisées.

## Conventions du projet

Lire les instructions du projet, la demande ou carte fournie et les README applicables.
Résoudre les chemins, couches, branches, commandes de tests et qualité depuis le projet ;
annoncer les valeurs utilisées et les inconnues, sans imposer de valeurs personnelles.
Avant une écriture, confirmer le worktree absolu, la branche autorisée et la disponibilité de la couche.
Préserver les modifications préexistantes et les `.env`. Ne pas utiliser stash, reset --hard,
force-push ou suppression de worktree pour résoudre une situation. Ne pas rebaser une branche occupée.
L’invocation autorise la livraison complète depuis la branche reconstituée : commits documentaires
nécessaires, vérification distante et fetch, push sans forcer, PR vers l’intégration, fusion après
contrôles et protections satisfaits, suivi local et suppression des branches temporaires livrées.
Ne pas redemander confirmation. Une instruction limitée à la PR ou une restriction explicite
du projet ou de l’utilisateur conserve sa limite.
Ne pas déléguer sans autorisation. Ne pas enchaîner automatiquement une autre étape.

## Procédure

Vérifier que l’étape 05 a réuni tous les commits validés sur une branche de demande.
Ne pas refaire la reconstitution ni la remplacer par des merges de branches de couche.
Contrôler la complétude, les verdicts, les SHA et le diff cumulé. Inventorier avant
livraison les worktrees, les missions, les modifications et les divergences locales.
Un arbre propre ne prouve pas la disponibilité d’une couche.

Dans AIDE, lire les règles d’intégration et de suivi communes dans
`docs/architecture/03-developpement-loop/06-livraison.md` et les autorisations
`AGENTS.md`. Pour la consolidation, lire aussi sa page de livraison. Ces références
fixent les préconditions du réalignement après réécriture des SHA, sans les dupliquer.
Respecter les limites explicites de l’utilisateur, notamment une demande limitée à la PR.

### Contrôles et PR

Faire réaliser les contrôles requis sur la branche reconstituée selon la règle commune et attendre leurs résultats.
Une preuve déjà lue portant sur le même HEAD, les mêmes commandes et le même environnement
peut éviter une répétition identique. Aucun contrôle inconnu ou échoué ne vaut réussite.
Ne pas affaiblir une règle, un seuil ou une exception pour livrer ; une correction
fonctionnelle retourne à la validation humaine. Les nouveaux contrôles de consolidation
disposent d’une commande stable et de cas conformes, écarts et exceptions testés.

Commiter seulement les traces documentaires nécessaires et autorisées. Vérifier remote,
authentification, branche source et cible, puis pousser sans forcer. Préparer la PR avec
le problème, le résultat final, les preuves et limites ; utiliser le connecteur disponible
ou gh avec --body-file. Reprendre une PR existante plutôt que la dupliquer. Une absence
d’accès laisse un dossier prêt et une cause précise, jamais une URL inventée.

### Intégration et suivi

Dans AIDE, intégrer vers develop par **Rebase and merge**, en conservant les commits
individuels sans commit de fusion ni squash. Vérifier que GitHub autorise la méthode,
les contrôles, revues et protections satisfaits, le HEAD exact et la cible. Ne pas
changer les protections ni employer un droit administrateur pour contourner un blocage.
Une méthode indisponible bloque l’intégration ; ne pas en substituer une autre.
Ne pas rebaser une branche partagée ou occupée pour préparer la PR.

Vérifier l’état intégré de la PR, le SHA résultant et sa présence dans la cible distante.
Tracer les correspondances source → reconstitution → commits réécrits. Une équivalence
de patch seule ne prouve jamais l’intégration distante. Les anciens merges restent intacts.

Suivre les règles communes du projet pour actualiser develop et réaligner les seules
couches locales confirmées libres, propres et sans travail inédit, malgré les nouveaux SHA.
Un rebase local sans commit à rejouer est permis uniquement dans les conditions explicites
du projet, après preuve d’intégration et correspondance de toutes les contributions ;
sinon préserver la branche et signaler la coordination nécessaire. Ni reset, stash,
force-push, suppression de worktree ni rebase d’une branche occupée ou partagée.

Préserver les .env, données et worktrees. Dans AIDE, ne pas publier les layers/* et
vérifier leur égalité de SHA avec develop avant de clôturer le suivi. Revenir sur
develop dans le principal libre et propre. Supprimer seulement les branches temporaires
réellement livrées, libres, sans autre PR ni travail inédit, selon la procédure commune,
sans suppression forcée. Ne jamais supprimer develop, master ou une branche de couche.

Consigner les SHA, l’URL réelle, les contrôles, l’alignement et les blocages dans la trace
existante. Ne pas modifier directement les fichiers suivis de develop pour ajouter ce
suivi. Ne pas ouvrir de PR vers master sans demande distincte. Une PR intégrée n’est pas
une preuve de déploiement. Ne pas annoncer la clôture si une couche reste non alignée.
Aucune délégation ni autre étape automatique.

## Sortie et preuve

Contributions contrôlées, commandes durables et dossiers de PR ; URLs seulement pour les PRs autorisées et réellement ouvertes ; SHA de fusion et suivi local lorsque demandés.

## Arrêt

Carte non validée, occurrence oubliée, contrôle requis inconnu ou échoué : ne pas ouvrir de PR et exposer le travail restant.
