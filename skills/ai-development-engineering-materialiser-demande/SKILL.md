---
name: ai-development-engineering-materialiser-demande
description: Matérialiser le brouillon confirmé d’une demande AIDE sur sa branche de reconstitution.
---

# Matérialiser une demande

Appliquer les instructions du projet et de l’étape appelante. Après reconstitution des commits validés, vérifier le dossier principal, sa branche `demands/<identifiant>`, l’index, les changements existants et la disponibilité de la mission avant écriture. Préserver le travail étranger, les données et les `.env`.

Rechercher le brouillon confirmé `tmp/demande-<sujet>.md` et tout document définitif existant de la même demande. Dans AIDE, matérialiser le brouillon sur la branche de demande dans `dev-book/demand/DEM-NNN-<sujet>.md`. Si le document existe déjà, le reprendre sans doublon ni écrasement de changements étrangers. Conserver le brouillon local ; cette matérialisation documentaire ne permet pas de copier du code non commité d’une autre mission.

Conserver l’identité, le type, la session d’origine et les sessions intervenantes, le cadrage confirmé, les décisions humaines, les verdicts et les références des commits. Adapter les liens vers les cartes au nouvel emplacement et conserver la correspondance des SHA sources et obtenus. Ne pas créer de rapport séparé. Le document et les traces de reconstitution peuvent rester non commités pour le commit documentaire de livraison, selon les autorisations du projet.

Vérifier le contenu et les liens ; restituer le chemin, les modifications et les limites. Si le brouillon, son identité, sa confirmation ou une référence nécessaire est absent ou contradictoire, préserver l’existant et signaler le blocage. Ne pas inventer de décision ni créer de commit, de PR ou de livraison.
