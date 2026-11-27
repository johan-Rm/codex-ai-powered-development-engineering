---
name: ai-development-engineering-materialiser-demande
description: Matérialiser le brouillon confirmé d’une demande AIDE dans son worktree dédié.
---

# Matérialiser une demande

Appliquer les instructions du projet et de l’étape appelante. À l’analyse, vérifier le worktree de la demande, sa branche `demands/<identifiant>-<sujet>`, l’index, les changements existants et la disponibilité de la mission avant écriture. Préserver le travail étranger, les données et les `.env`.

Rechercher le brouillon confirmé `tmp/demande-<sujet>.md` dans le dépôt principal et tout document définitif existant de la même demande. Dans AIDE, matérialiser le brouillon sur la branche de demande dans `dev-book/demand/DEM-NNN-<sujet>.md`. Si le document existe déjà, le reprendre sans doublon ni écrasement de changements étrangers. Conserver le brouillon local ; cette matérialisation documentaire ne permet pas de copier du code non commité d’une autre mission.

Conserver l’identité, le type, la session d’origine et les sessions intervenantes, le cadrage confirmé, les décisions humaines, les verdicts et les références des commits. Adapter les liens vers les cartes au nouvel emplacement et conserver les références historiques de commits. Ne pas créer de rapport séparé. Le document et les cartes préparés à l’analyse restent disponibles pour l’implémentation selon les autorisations du projet.

Vérifier le contenu et les liens ; restituer le chemin, les modifications et les limites. Si le brouillon, son identité, sa confirmation ou une référence nécessaire est absent ou contradictoire, préserver l’existant et signaler le blocage. Ne pas inventer de décision ni créer de commit, de PR ou de livraison.
