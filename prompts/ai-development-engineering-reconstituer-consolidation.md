---
description: "Réunir les commits des cartes de consolidation validées sur une branche de demande depuis develop, avec traçabilité des SHA et contrôles."
---

# Consolidation · 05 Reconstitution

Avant toute autre lecture liée à la mission, lire le chapitre « Règles de rédaction des réponses et des documents » du `AGENTS.md` applicable.
Appliquer les règles de tests lourds du chapitre « Contrôles qualité et conditions de clôture du travail » d’AGENTS.md.

## Entrée

Demande de consolidation et toutes ses cartes commitées à l’étape 03 puis validées à l’étape 04,
avec verdicts, SHA sources et ordre des dépendances.

## Procédure

Lire les instructions, les README, la demande et les cartes. Dans AIDE, appliquer
la procédure commune `docs/architecture/03-developpement-loop/05-reconstitution.md`.
La référence de consolidation est `docs/architecture/04-consolidation-loop/05-reconstitution.md`.
Rester concis et renvoyer aux décisions existantes sans les recopier.

Vérifier la disponibilité, la branche, l’index et tous les fichiers non suivis du
dossier principal. Préserver les .env, données, fichiers locaux et worktrees.
Ne pas déplacer une mission étrangère ni utiliser stash, reset destructif ou force-push.

L’invocation autorise la création de `demands/<identifiant>` depuis le develop local
vérifié, dans le dossier principal libre et propre, puis les cherry-picks `-x` des
seuls commits validés. Les couches conservent leurs branches. Une reprise vérifie
provenance et contenu des commits déjà réunis pour ne pas les rejouer.
Ne pas merger les branches de couche ni copier du travail non commité.

Consigner la correspondance source → obtenu dans la demande ou les cartes ;
préserver les identifiants et sessions réels. Reprendre le document existant sans
doublon ; matérialiser un brouillon confirmé seulement si le projet le prévoit.
Vérifier le diff, les liens et les contrôles. Un conflit qui change le résultat
validé demande une décision humaine ; ne pas valider une différence par déduction.
Aucun nouveau développement, push, PR, fusion de livraison ou étape suivante automatique.
Ne pas déléguer sans demande explicite.

## Sortie et preuve

Branche dédiée reconstituée, SHA sources et obtenus, contrôles et limites dans la
trace de la demande, prête pour l’étape 06 Livraison.

## Arrêt

Carte non validée, commit manquant, dossier sale ou occupé, branche étrangère ou
conflit hors du résultat validé : préserver le travail et exposer le blocage.
