---
name: ai-development-engineering-fusionner-pr
description: Fusionner une PR AIDE autorisée après vérification des contrôles et protections.
---

# Fusionner une pull request

Respecter les instructions du projet, les autorisations déjà données et les limites explicites de l’utilisateur. Une demande limitée à la PR ne permet pas de fusionner. Ce skill n’autorise aucune action supplémentaire. Consulter la référence commune `/home/johan/.codex/skills/references/git-workflow.md`.

Vérifier la PR réelle, sa branche source, sa cible, son HEAD exact, les verdicts, les contrôles, revues et protections requis. Un résultat inconnu ou échoué bloque la fusion. Vérifier que la méthode autorisée est disponible ; ne pas modifier les protections ni les contourner avec un droit administrateur.

Pour une livraison AIDE de développement ou de consolidation, transmettre à l’humain la PR et le message du commit unique prévu par la référence Git commune. L’humain effectue le Squash and merge vers `develop` après vérification des contrôles et protections. Signaler tout blocage de la méthode prévue. Préserver les branches partagées ou occupées.

Après fusion, vérifier l’état intégré de la PR, le SHA résultant et sa présence dans la cible distante. Tracer la correspondance entre commits sources, reconstitués et réécrits ; une équivalence de patch seule ne prouve pas l’intégration. Restituer l’URL réelle, le HEAD vérifié, les contrôles et le SHA intégré. Une PR fusionnée ne prouve pas un déploiement. Le suivi local relève de l’étape appelante.
