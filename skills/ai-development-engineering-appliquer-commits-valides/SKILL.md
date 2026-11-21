---
name: ai-development-engineering-appliquer-commits-valides
description: Appliquer et tracer les commits validés d’une demande AIDE sur sa branche de reconstitution.
---

# Appliquer les commits validés

Respecter les consignes du projet et les autorisations de l’étape appelante ; ce skill n’autorise aucune opération Git supplémentaire. Identifier les cartes et leurs verdicts explicites, les commits sources validés, les commits documentaires de verdict nécessaires et l’ordre des dépendances. Une carte non validée, un commit manquant ou une provenance ambiguë bloque son application.

Vérifier le chemin absolu du dépôt principal, la branche de demande, l’index, les fichiers non suivis, le travail existant et les missions actives. Préserver les changements identifiés d’une reprise et refuser une branche étrangère ou un travail incompatible. Préserver les couches, les `.env`, les données et les worktrees ; ne pas utiliser stash, reset destructif ou force-push.

Appliquer sur la branche de demande les seuls commits autorisés et validés, dans l’ordre des dépendances, par cherry-pick avec provenance (`git cherry-pick -x`). Avant une reprise, vérifier la provenance et le contenu des commits déjà présents pour ne pas les appliquer deux fois. Ne pas fusionner les branches de couche ni copier leur travail non commité.

Consigner la correspondance des SHA source et obtenu dans la demande ou les cartes, selon le projet, sans créer de rapport supplémentaire. Un conflit se résout uniquement dans le périmètre validé ; si la résolution modifie le résultat validé, attendre une décision humaine. Ne pas déduire une nouvelle validation. En cas de blocage, préserver l’état et exposer les éléments à résoudre.

Vérifier le résultat, les références et les contrôles proportionnés selon les règles du projet. Restituer les SHA réels, les vérifications et leurs limites. Ne pas pousser, ouvrir de PR, fusionner ou enchaîner une autre étape.
