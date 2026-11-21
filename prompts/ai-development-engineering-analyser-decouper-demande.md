---
description: "Analyser une demande de développement, ses impacts et dépendances, puis préparer toutes ses cartes et missions."
---

# Développement · 02 Analyse / découpage

Avant toute autre lecture liée à la mission, lire le chapitre « Règles de rédaction des réponses et des documents » du `AGENTS.md` applicable.
Appliquer les règles de tests lourds du chapitre « Contrôles qualité et conditions de clôture du travail » d’AGENTS.md.

## Entrée

Demande cadrée et décisions humaines identifiées.

## Conventions du projet

Lire les instructions du projet, la demande ou carte fournie et les README applicables.
Les instructions explicites de l’utilisateur priment sur les règles locales.
Résoudre les chemins, couches, branches, commandes de tests et qualité depuis le projet ;
annoncer les valeurs utilisées et les inconnues, sans imposer de valeurs personnelles.
Avant une écriture, confirmer le worktree absolu, la branche autorisée et la disponibilité de la couche.
Préserver les modifications préexistantes et les `.env`. Ne pas utiliser stash, reset --hard,
force-push ou suppression de worktree pour résoudre une situation. Ne pas rebaser une branche occupée.
Respecter les autorisations Git du projet : une invocation peut autoriser les commits locaux
prévus par cette étape si le projet le définit explicitement. Push, PR et merge restent soumis
à leurs autorisations propres. Conserver les autorisations explicites déjà données.
Ne pas déléguer sans autorisation. Ne pas enchaîner automatiquement une autre étape.

## Procédure

Analyser le besoin, les impacts et les conventions applicables avant de découper.
Comparer les options utiles et faire confirmer les décisions de besoin encore ouvertes,
sans redemander celles déjà explicites. La sortie couvre toutes les cartes de la demande.

Dans AIDE, lire le brouillon `tmp/demande-<sujet>.md` depuis la racine du dépôt
principal ; la demande définitive n’existe pas encore. Mettre à jour ce brouillon
avec la matrice des cartes, sans le copier dans un worktree. Les cartes restent
versionnées dans dev-book/tasks/ de leur couche. Chaque carte identifie le brouillon
par son chemin relatif au dépôt principal et prévoit le lien vers la demande
définitive ; ne pas présenter ce lien futur comme un fichier existant.

Répartir les responsabilités selon le routage du projet, sans inventer de couche. Pour chaque carte,
fixer objectif, exclusions, chemins autorisés, critères, tests proportionnés, documentation, preuve,
worktree relatif au dépôt principal et branche ; annoncer le chemin absolu résolu dans le chat.
Distinguer les dépendances de réalisation des dépendances de vérification globale.
Seules les premières bloquent l’implémentation : identifier les commits nécessaires ;
une tâche amont sans commit reste à résoudre avant son consommateur.
Prévoir les contrôles d’ensemble après réunion des commits sans bloquer les changements indépendants. Vérifier la complétude par rapport à la demande.
Attribuer les identifiants depuis l’historique de toutes les références locales et les fichiers des
worktrees concernés, sans fetch implicite. Renseigner dans chaque carte l’identifiant réel de la session de création, issu du contexte
ou d’une source locale fiable (par exemple CODEX_THREAD_ID ou CODEX_SESSION_ID). Son absence
ou une contradiction entre sources bloque la création : signaler le problème sans inventer
d’identifiant ni écrire une mention d’indisponibilité. Une reprise conserve l’identifiant
d’origine et ajoute celui de la session intervenante.
Réaliser le découpage en autonomie ; questionner seulement une décision de besoin manquante.
Prévoir la branche `demands/<identifiant>`, créée à la reconstitution depuis develop
local vérifié dans le dossier principal du dépôt (worktree relatif `.`). Les
worktrees de couche conservent layers/* pour les missions ; ne pas y placer la
branche finale d’une nouvelle demande. Le dossier principal doit être libre et
propre à la reconstitution ; s’il est occupé par une autre demande, annoncer
l’attente sans déplacer cette mission. Prévoir le retour du principal sur develop
après fusion distante, sans contribution directe sur develop. Ne créer la branche
de demande qu’à la reconstitution. Aucune copie ou dossier de réunion supplémentaire.
La branche dédiée reste distincte de develop et de production, même pour une couche.
Préparer les branches dans les worktrees affectés,
après vérification des missions actives ; conserver une branche existante sans rebase implicite.
Une base locale explicite suffit si le projet le prévoit ; ne pas annoncer de synchronisation distante.
Ne pas implémenter les cartes.

## Sortie et preuve

Cartes et matrice demande/tâches, ordre et dépendances, état réel des branches préparées. Preuve : chemins des cartes et états Git observés.

## Arrêt

Couche occupée, identifiant ambigu ou dépendance de réalisation sans commit : signaler les missions non prêtes sans copier le travail non commité.
