---
description: "Créer la branche d’une demande depuis develop et y cherry-pick les commits validés."
---

# Développement · 05 Reconstitution

Avant toute autre lecture liée à la mission, lire le chapitre « Règles de rédaction des réponses et des documents » du `AGENTS.md` applicable.
Appliquer les règles de tests lourds du chapitre « Contrôles qualité et conditions de clôture du travail » d’AGENTS.md.

## Entrée

Demande, cartes validées, SHA de leurs commits et branche dédiée prévue au découpage.

## Procédure

Lire les consignes du projet, la demande, les cartes et les README applicables.
Les instructions explicites de l’utilisateur priment sur les règles locales.
Vérifier que toutes les cartes attendues sont validées et commitées. Inclure les
commits de verdict nécessaires et respecter l’ordre des dépendances.

Dans AIDE, utiliser le dossier principal du dépôt, pas un worktree de couche.
Résoudre son chemin absolu depuis git worktree list, sans confondre cette racine
avec git rev-parse --show-toplevel exécuté dans un worktree lié. Vérifier sa
branche, son index, les fichiers non suivis et les missions actives. Pour une
nouvelle reconstitution, le principal doit être libre et propre, sur develop.
S’il porte une autre demande ou des changements étrangers, signaler le blocage
sans déplacement, stash ou nettoyage. Une reprise de la même demande conserve
ses changements identifiés après vérification ; ne pas déplacer une demande
ancienne déjà reconstituée dans une couche sans instruction explicite.
Préserver tmp/, les .env, données et fichiers locaux. Ne créer ni nouveau
worktree, copie ou dossier de réunion. Les worktrees de couche restent sur layers/*.

Dans le principal, créer `demands/<identifiant>` depuis le develop local
explicitement vérifié : `git switch -c demands/<identifiant> develop`.
Ne pas modifier directement develop ou production. Une branche existante n’est
pas déplacée : vérifier sa provenance et reprendre seulement la même demande.
Noter develop comme branche à retrouver dans le principal après fusion distante.

Appliquer les seuls commits validés avec `git cherry-pick -x <sha>`, dans l’ordre.
Ne pas merger les branches de couche pour reconstituer la demande, ni copier des
fichiers non commités. Garder la provenance source → commit obtenu dans la demande
ou les cartes, sans rapport séparé. Avant une reprise, vérifier les cherry-picks
déjà présents par leur provenance et contenu pour ne pas les appliquer deux fois.
Les SHA obtenus peuvent différer des SHA sources validés.

Après les cherry-picks, matérialiser le brouillon `tmp/demande-<sujet>.md` du
principal dans `dev-book/demand/DEM-NNN-<sujet>.md` sur la branche de demande.
Conserver l’identité, la session d’origine et les sessions intervenantes, le
cadrage confirmé, les décisions, verdicts et références de commits. Adapter
les liens vers les cartes à cet emplacement et consigner les SHA source → obtenu.
S’il existe déjà un document définitif de cette demande, le reprendre sans doublon.
Le brouillon local n’est pas une contribution de code non commitée d’une autre
mission : seule cette matérialisation documentaire explicitement prévue est permise.
Conserver le brouillon et ne pas créer de rapport séparé. Les cartes sont déjà
versionnées par leurs commits validés. Le document définitif et les traces de
reconstitution peuvent rester non commités pour le commit documentaire de livraison.

Vérifier le diff final, les liens et les contrôles pertinents. Un conflit se résout
uniquement dans le périmètre validé ; si sa résolution change le comportement,
attendre une décision humaine. Ne pas revalider un résultat différent par déduction.
L’invocation autorise la création de branche et les cherry-picks du périmètre prévu ;
respecter les restrictions explicites du projet et de l’utilisateur.
Ne pas stasher, reset destructivement, forcer une référence ou rebaser une branche
occupée. Aucune délégation, push, PR, fusion de livraison ou étape suivante automatique.

## Sortie et preuve

Branche dédiée reconstituée, correspondance des SHA sources et obtenus, diff et
contrôles, limites éventuelles consignés dans la demande ou les cartes.

## Arrêt

Carte non validée, commit absent, worktree sale ou occupé, branche étrangère ou
conflit hors du résultat validé : préserver le travail et signaler le blocage.
