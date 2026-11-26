---
name: ai-development-engineering-commit
description: Préparer et créer un commit Git autorisé en respectant la traçabilité AIDE et les conventions du projet.
---

# Créer un commit AIDE

Lire d’abord les règles de rédaction et de contrôles du `AGENTS.md` applicable, puis la référence commune `/home/johan/.codex/skills/references/git-workflow.md`. Créer un commit uniquement si l’utilisateur ou l’étape active l’autorise ; l’invocation de ce skill n’ajoute aucune autorisation Git.

Identifier les fichiers et modifications de la tâche, puis indexer uniquement le contenu autorisé. Relire le diff indexé avant de committer. Ne pas effectuer de push, amend ou réécriture d’historique sans autorisation distincte.

Déterminer le format du message, les identifiants de traçabilité et les éventuelles restrictions de scope à partir des conventions du dépôt et de ses contrôles. Rédiger un titre qui exprime le résultat concret du changement.

Utiliser le vérificateur du projet pour le message et, lorsque nécessaire, la plage de commits avec une base explicite ; un contrôle du seul message ne vérifie ni les fichiers ni les références. La validation d’une contribution repose sur le vérificateur extrait de la base d’intégration, pas sur celui modifié par la contribution.

Après création, relever le SHA réel et signaler le périmètre, les contrôles et leurs limites. Un commit technique ne vaut pas validation humaine.
