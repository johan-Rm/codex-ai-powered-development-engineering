---
name: ai-development-engineering-preparer-cartes
description: Préparer les cartes et dépendances d’une demande AIDE analysée, selon les couches et conventions du projet.
---

# Préparer les cartes d’une demande

Lire les consignes, la demande matérialisée et les décisions confirmées. Vérifier le chemin absolu du worktree unique de la demande, sa branche, son index, ses fichiers non suivis et sa disponibilité ; préserver les changements existants. Une reprise conserve le travail identifié de la même demande. Un arbre propre ne prouve pas la disponibilité.

Préparer dans ce worktree toutes les cartes et leur matrice selon les conventions du projet. Identifier pour chaque tâche sa couche technique, son objectif, ses exclusions, ses chemins, critères, contrôles, documentation et preuves. Les couches décrivent les responsabilités ; elles ne désignent ni branche ni worktree de mission. Vérifier la couverture et distinguer les dépendances de réalisation des contrôles d’ensemble.

Attribuer les identifiants depuis les références Git locales et les fichiers pertinents sans fetch implicite. Renseigner la session réelle de création depuis une source fiable ; une absence ou contradiction bloque la création. Une reprise conserve la session d’origine et ajoute celle de l’intervenant. Ne pas inventer d’identifiant.

La création ou la reprise du worktree et de sa branche est régie par l’étape appelante ; ce skill ne confère aucune autorisation Git supplémentaire. Ne pas implémenter les cartes, copier du code non commité entre missions ni réécrire une branche. Restituer chemins, matrice, dépendances, état Git et blocages.
