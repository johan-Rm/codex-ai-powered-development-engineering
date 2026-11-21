---
name: ai-development-engineering-documenter-projet
description: Préparer puis intégrer la documentation docs d’une demande AIDE selon son étape de travail.
---

# Documenter le projet

Lire `/home/johan/.codex/skills/references/documentation.md`, les instructions et conventions documentaires applicables au projet. Respecter l’étape appelante, les chemins autorisés et les décisions humaines ; ce skill ne crée aucune autorisation Git supplémentaire.

## Pendant l’implémentation

Identifier les sujets documentaires impactés et leurs sources existantes. Préparer les ajouts ou modifications de `docs/` dans un brouillon identifié par la carte, à un emplacement versionné autorisé par le projet, hors de `docs/`. Décrire les destinations prévues, les liens et déplacements nécessaires. Inclure ce brouillon dans le commit de la tâche pour qu’il puisse être examiné à la vérification puis récupéré par la reconstitution ; ne pas copier du travail non commité entre worktrees. Signaler une destination ou autorisation indéterminée au lieu d’inventer un chemin. Les README et autres documents hors `docs/` suivent leurs propres règles et le périmètre de la carte.

## Pendant la reconstitution

Après application des commits validés, retrouver les brouillons documentaires de la demande dans les commits réunis et vérifier qu’ils correspondent au contenu présenté à l’humain et à son verdict. Intégrer dans `docs/` les seuls changements documentaires validés, selon la référence, sans écraser le travail existant ; adapter les sommaires et les liens concernés en préservant les traces historiques. Ne pas modifier le résultat validé par déduction : signaler tout contenu manquant, divergence ou décision nécessaire et attendre sa résolution. Ne créer ni commit ni livraison sans autorisation de l’étape.

Vérifier le diff, la structure et les liens avec les contrôles adaptés disponibles, dans les limites des règles de tests lourds. Documenter les résultats et limites ; une vérification technique ne remplace pas la relecture humaine. Restituer les documents et les blocages éventuels.
