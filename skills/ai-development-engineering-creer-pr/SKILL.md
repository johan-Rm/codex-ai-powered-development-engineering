---
name: ai-development-engineering-creer-pr
description: Préparer et créer une pull request autorisée à partir d’une contribution vérifiée, sans la fusionner.
---

# Créer une pull request

Lire d’abord les règles de rédaction et de contrôles du `AGENTS.md` applicable, puis la référence commune `/home/johan/.codex/skills/references/git-workflow.md`. Ne créer ou modifier une PR et ne pousser une branche que dans leur périmètre autorisé ; l’invocation de ce skill ne permet pas de fusionner.

Identifier le dépôt distant, la branche source, la cible d’intégration et le HEAD ; vérifier l’authentification et les conventions du projet. Examiner les commits et le diff complet de la contribution par rapport à la cible vérifiée, ainsi que les preuves et contrôles requis. Un contrôle requis inconnu ou échoué bloque l’ouverture ; signaler son état et poursuivre les préparatifs indépendants.

Vérifier si une PR existe déjà pour la même source et la même cible ; la reprendre selon les autorisations plutôt que la dupliquer. Si un push est nécessaire et autorisé, pousser sans forcer, puis vérifier la branche distante et le HEAD publié.

Rédiger un titre et une description adaptés au résultat final et au modèle du dépôt : problème, comportement obtenu, contrôles réalisés et limites. Pour une livraison AIDE, appliquer la référence commune au titre de PR et au message de squash préparé, distinctement des commits de contribution ; utiliser les vérificateurs disponibles ou demander la vérification humaine prévue. Utiliser le connecteur disponible ou `gh` ; pour un corps multiligne avec `gh`, utiliser un fichier passé à `--body-file`. Créer la PR sur la cible autorisée, puis vérifier son URL, sa source et sa cible. Signaler les contrôles distants en attente ou échoués sans les présenter comme réussis.

Restituer le lien réel, les branches, le HEAD, les vérifications et les éventuels blocages. Une PR ouverte ne signifie ni fusion, ni livraison terminée, ni déploiement. En cas d’accès manquant, conserver la description prête et indiquer la cause ; ne pas inventer d’URL.
